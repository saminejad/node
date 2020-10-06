const express = require('express')
const app = express()
const url = require('url')
const qs = require('querystring')

app.get("/", (req, res) => {


    let data = url.parse(req.url).query.replace(/[^ a-z A-Z 0-9 =]/g, '')

    console.log(qs.parse(data))

    res.send("hello")





})

app.listen(3000)
