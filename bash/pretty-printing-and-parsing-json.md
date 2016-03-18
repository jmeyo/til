# Pretty-Print JSON Blobs On The Command Line

Pretty printing JSON is easy with either jq or python.tool. The jq tool has the advantage of applying filters for quickly parsing large JSON blobs or setting exit codes based on output for use in scripting.

Pretty print all of the JSON.
`$ echo '{"foo": "bar"}' | python -m json.tool`
`$ echo '{"foo": "bar"}' | jq '.'`

Get just the output of foo.
`$ echo '{"foo": "bar"}' | jq '.foo'`
