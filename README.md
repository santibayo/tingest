# tingest
tshark ingestion fluent-bit for dns traffic

## Fluent-bit ingestion.
this piece of code listens for tcp connections at port 8888 and writes the json captured data in a file:

`fluent-bit -i tcp -p port=8888 -p listen=0.0.0.0 -o file -p path=/tmp/fluent -p format=plain -p file=output -p mkdir=true -vvv`


## Tshark capture.
`sudo tshark -f "src port 53" -n -T ek|nc 127.0.0.1 8888`

