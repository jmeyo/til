# File Transfer Alternatives

When you don't have ftp, sftp, rsync or other file transfer protocols at your disposal -- or are being blocked -- there are a few creative ways to still transfer what you need.

## cat Over SSH

`cat LOCALFILE | ssh user@remotehost 'cat > REMOTEFILE'`

## cat Over netcat (pull from server)

### To Serve
`cat ${FILE} | nc -l -p ${PORT}`

### To Receive
`nc ${SERVER} ${PORT} > ${FILE}`

## cat Over netcat (send to server)

### To Send
`cat ${FILE} | nc ${SERVER} ${PORT}`

### To Receive
`nc -l -p ${PORT} -q 1 > ${FILE} < /dev/null`

## Serve Directory Over HTTP and Pull with wget

### To Serve
`python -m SimpleHTTPServer ${PORT}`

### To Receive
`wget http://${SERVER}:${PORT}/${FILE}`
