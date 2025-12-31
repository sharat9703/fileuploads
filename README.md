# File Metadata Microservice

A REST API that analyzes uploaded files and returns metadata including filename, file type, and size.

## Features

- Upload any file through a simple web interface
- Get instant file metadata (name, type, size)
- CORS enabled for cross-origin requests

## Technologies Used

- **Node.js** - Runtime environment
- **Express** - Web framework
- **Multer** - Middleware for handling multipart/form-data (file uploads)
- **CORS** - Cross-Origin Resource Sharing

## Setup

1. Clone the repository
2. Install dependencies:
   ```bash
   npm install
   ```
3. Start the server:
   ```bash
   npm start
   ```
4. Open your browser and navigate to `http://localhost:3000`

## API Endpoint

### Analyze File
**POST** `/api/fileanalyse`

Upload a file using multipart/form-data with the field name `upfile`.

**Request:**
- Content-Type: `multipart/form-data`
- Field name: `upfile`
- File: Any file type

**Response:**
```json
{
  "name": "example.txt",
  "type": "text/plain",
  "size": 1024
}
```

**Response Fields:**
- `name` - Original filename
- `type` - MIME type of the file
- `size` - File size in bytes

## Usage Example

Using curl:
```bash
curl -X POST -F "upfile=@/path/to/your/file.txt" http://localhost:3000/api/fileanalyse
```

Using the web interface:
1. Navigate to `http://localhost:3000`
2. Click "Choose File" and select any file
3. Click "Upload"
4. View the file metadata in the response

## Error Handling

If no file is uploaded, the API returns:
```json
{
  "error": "No file uploaded"
}
```

## License

MIT