# ARCHIVED

This repository is archived. I am no longer actively developing/supporting it.

If you are interested in discussing the contents of this repository feel free to contact me
via the contact details provided in the "Author" section below.

Note: This code didn't use the correct streaming APIs, and so could not handle large files.

# archstor

v0.1.2

[![Build Status](https://travis-ci.org/bnbalsamo/archstor.svg?branch=master)](https://travis-ci.org/bnbalsamo/archstor) [![Coverage Status](https://coveralls.io/repos/github/bnbalsamo/archstor/badge.svg?branch=master)](https://coveralls.io/github/bnbalsamo/archstor?branch=master)

Archstor is a web API wrapper which provides a simplified API for several object storage backends/interfaces.

# Debug Quickstart
Set environmental variables appropriately
```
./debug.sh
```

# Docker Quickstart
Inject environmental variables appropriately at either buildtime or runtime
```
# docker build . -t archstor
# docker run -p 5000:80 archstor --name my_archstor
```

### /
### GET
#### Args
- offset (int): A listing offset
- limit (int): A suggested number of returned listing values
#### Returns
```{"objects": ["identifier": <object_id>, "_link": <object_link> for each object in the listing], "pagination": {"cursor": <listing_cursor>, "limit": <listing_limit>, "next_cursor": <next_cursor_to_continue_listing>}}```

---

## /\<string:identifier\>
### GET
#### Returns
The object bytestream
### PUT
#### Args
- object: The bytestream to store
#### Returns
```{"identifier": <id>, "added": True}```
### DELETE
#### Returns
```{"identifier": <id>, "deleted": True}```

# Currently Supported Backends

- GridFS
- swift

# On the docket

- s3


# Environmental Variables
* #TODO


# Author
Brian Balsamo <brian@brianbalsamo.com>
