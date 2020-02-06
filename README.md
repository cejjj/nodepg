# Database2 nodepg

## this is my activity in database 2 and the important codes/snippets are the following:
1. require('dotenv').config()
const {Pool} = require('pg')

const pool = new Pool({
    user: `${process.env.DB_USER}`,
    host: `${process.env.DB_HOST}`,
    database: `${process.env.DB_DATABASE}`,
    password: `${process.env.DB_PASSWORD}`,
    port: 5432,
    ssl: {
        rejectUnauthorized:false,
    }})

pool.query('SELECT * FROM books', (error, results) => {
if (error){
    throw error
}
console.log(results.rows)
})

## in case of error [Type of error], here are the steps that you need to consider:
1. Error: getaddrinfo ENOTFOUND undefined
    at GetAddrInfoReqWrap.onlookup [as oncomplete] (dns.js:60:26) {
  code: 'ENOTFOUND',
  syscall: 'getaddrinfo',
  hostname: 'undefined'
}

2. SyntaxError: Unexpected end of input
    at Module._compile (internal/modules/cjs/loader.js:891:18)
    at Object.Module._extensions..js (internal/modules/cjs/loader.js:991:10)
    at Module.load (internal/modules/cjs/loader.js:811:32)
    at Function.Module._load (internal/modules/cjs/loader.js:723:14)
    at Function.Module.runMain (internal/modules/cjs/loader.js:1043:10)
    at internal/main/run_main_module.js:17:11