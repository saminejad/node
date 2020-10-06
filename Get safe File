const http = require('http')
const url = require('url')
const fs = require('fs')
const qs = require('querystring')
const mime = require('mime')

http.createServer((req, res) => {


    let uri = __dirname + "/safe" + url.parse(req.url).pathname

    fs.readFile(uri, (err, data) => {
        if (!err) {
            res.writeHead(200, { 'content-type': mime.getType(uri) })
            res.end(data)
        }
        else {
            res.writeHead(404, { 'content-type': 'text/html' })
            res.end("File Not Found")
        }
    })


}).listen(3000)
