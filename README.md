### Token Mining Pool  

Developed by the 0xBitcoin Community

(GNU PUBLIC LICENSE)

A pool for mining RC20 Tokens

CSS Colors: https://flatuicolors.com/palette/au

1) improve colors
2) more workers  (jsonrpc listeners?)
3) two eth accounts .. xfers and mints
4) separate geth
5) why does it say 'Reply:OK' ??

上传文件到服务器

### BASIC SETUP  (needs Node8)
1. curl -sL https://deb.nodesource.com/setup_8.x | sudo -E bash -

   sudo apt-get install -y nodejs
                                                                             //npm install -g node-gyp
2. sudo apt-get install build-essential
3. npm install
4. npm run webpack  #(to build the website files)
5. rename 'sample.account.config.js' to 'account.config.js' and fill it with the pool's ethereum account data

6. install redis-server and make sure it is running
7. Edit pool.config.js to your tastes
8. Edit the website files in /app  to change the look of the website
9. npm run server #(or npm run server test for Ropsten test net)


### HOW TO USE
1. Point a poolminer at your pool using http://localhost:8586  (or ipaddress:8586 or domain.com:8586)  (make sure firewall allows this port)
2. View website interface at http://localhost:3000 (you can set up nginx to serve the static files in /public)


## Installing Redis  
  1. sudo apt-get install redis-server
  1.1检查Redis服务器系统进程
  ps -aux|grep redis
  1.2通过启动命令检查Redis服务器状态
  netstat -nlt|grep 6379
  1.3通过启动命令检查Redis服务器状态
  sudo /etc/init.d/redis-server status
  
  2. sudo service redis-server start

   - Redis will serve/connect at localhost:6379 by default - the pool will use this port

## Redis Commands

LRANGE broadcasted_payments 0 -1




## TODO / BUGS
- Add more clustering/workers and more JSONRPC/socket ports to handle heavy loads
- Make sure good solns ARE BEING TRANFERRED
