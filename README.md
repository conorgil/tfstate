# tfstate - Easily get output from terraform state

`tfstate` is a convenience tool that can output terraform output as a JSON
object from any supplied terraform state. The terraform state references are
loaded using a uri format.

## Key Features

* Supports Remote State (S3 only at the moment)
* Uses a default 60 second cache to reduce network overhead and increase speed of query

## CLI Usage

Get the terraform output for the state stored in an s3 bucket `mybucket` and the
path `infrastructure/production`:

    $ tfstate --state-uri=s3://mybucket/infrastructure/production

## Library Usage

Usage in a library is also equally as simple:

    import tfstate

    state_uri = "s3://mybucket/infrastructure/production"

    output = tfstate.get(state_uri)

The `output` object is simply a dictionary of the terraform output
