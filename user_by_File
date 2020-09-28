const crypto = require('crypto')
const fs = require('fs')
const qs = require('querystring')


let myUser = (id, pass, flag) => {

    let path = __dirname + "/users/"
    let cid = cryptoId(id)
    let cp = cryptoPass(pass)

    // check user 
    fs.stat(path + cid, (err, stat) => {
        if (stat) {

            // if user login 
            flag == 1 ? checkUsr(id, pass) : console.log("user exist")
        }
        else {
            let mydata =
            {
                pass: cp
            }

            fs.writeFile(path + cid, JSON.stringify(mydata), () => { })

        }



    })

}

let cryptoId = (id) => {
    return crypto.createHmac("sha256", "Bssbsx123").update(id + "43994399").digest("hex")
}

let cryptoPass = (pass) => {
    return crypto.createHmac("sha256", "Bsx123bsx").update(pass + "80218021").digest("hex")

}

let checkUsr = (id, pass) => {

    let path = __dirname + "/users/" + cryptoId(id)
    fs.readFile(path, (err, data) => {
        if (!err) {
            let usrpass = JSON.parse(data).pass
            usrpass == cryptoPass(pass) ? console.log("loged in") : console.log("invalid user info ")



        }
    })

}



myUser("fati", "46121")
