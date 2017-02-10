# Api


## Starting server


```shell
$ npm install
$ node .
```

## Models
Person [extends User]
* firstName*: string
* lastName*: string
* npi*: string
* city: string
* state: string
* email*: string
* password*: string
* info: string
* title*: string
* profileImage: string

Category
* title*: string
* description: string
* image*: string

Device
* name*: string
* category*: ObjectId
* image*: string
* website*: string
* description: string

Review
* user*: ObjectId
* device:* ObjectId
* rating*: number
* comment: string

Question
* user*: ObjectId
* title*: string
* description*: string


Relations
* Person has_many Reviews
* Person has_many Questions
* Category has_many Devices
* Device has_many Reviews
* Device belongs_to category
* Review belongs_to Person
* Review belongs_to Device 
* Question belongs_to Person

**API**
Once you create a container, it will provide both a REST and Node API, as described in the following table.

<table>
  <tbody>
    <tr>
      <th>Description</th>
      <th>
        <p>Container Model Method</p>
      </th>
      <th>REST URI</th>
    </tr>
    <tr>
      <td>List all containers.</td>
      <td>
        <p>getContainers(cb)</p>
        <div style="300px;">
          <p>&nbsp;</p>
        </div>
      </td>
      <td><span>GET<br></span><span>/api/containers</span></td>
    </tr>
    <tr>
      <td>Get information about specified container.</td>
      <td>getContainer(container, cb)</td>
      <td><span>GET<br></span><span>/api/containers/:container</span></td>
    </tr>
    <tr>
      <td>Create a new container.</td>
      <td>createContainer(options, cb)</td>
      <td><span>POST<br></span><span>/api/containers</span></td>
    </tr>
    <tr>
      <td>Delete specified container.</td>
      <td>destroyContainer(container, cb)</td>
      <td><span>DELETE<br></span><span>/api/containers/:container</span></td>
    </tr>
    <tr>
      <td>List all files within specified container.</td>
      <td>getFiles(container, download, cb)</td>
      <td><span>GET<br></span><span>/api/containers/:container/files</span></td>
    </tr>
    <tr>
      <td>Get information for specified file within specified container.</td>
      <td>getFile(container, file, cb)</td>
      <td><span>GET<br></span><span>/api/containers/:container/files/:file</span></td>
    </tr>
    <tr>
      <td>Delete a file within a given container by name.</td>
      <td>removeFile(container, file, cb)</td>
      <td><span>DELETE </span><span>/api/containers/:container/files/:file</span></td>
    </tr>
    <tr>
      <td>Upload one or more files into the specified container. The request body must use multipart/form-data which the file input type for HTML uses.</td>
      <td>upload(req, res, cb)</td>
      <td><span>POST<br></span><span>/api/containers/:container/upload</span></td>
    </tr>
    <tr>
      <td>Download a file within specified container.</td>
      <td>download(container, file, res, cb)</td>
      <td><span>GET<br></span><span>/api/containers/:container/download/:file</span></td>
    </tr>
    <tr>
      <td>Get a stream for uploading.</td>
      <td><span>uploadStream(container, file, options, cb)</span></td>
      <td>&nbsp;</td>
    </tr>
    <tr>
      <td>Get a stream for downloading.</td>
      <td><span>downloadStream(container, file, options, cb)</span></td>
      <td>&nbsp;</td>
    </tr>
  </tbody>
</table>
