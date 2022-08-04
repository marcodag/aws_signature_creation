# aws_signature_creation
this repo contains the generic Java algorithm to create AWS signature for accessing s3 private buckets.

The algorithm was tested OK for retrieving (GET) an object from an s3 private bucket, without any query parameters, following https://docs.aws.amazon.com/AmazonS3/latest/API/sig-v4-header-based-auth.html guidelines.
The right signature's output was tested by doing the call on Postman, with AWS headers. The call created an Authorization header that contained the signature.
Then, by using the X-Amz-Date header's value as the algorithm's input (together with host, bucket, token, ...), the signature so-being produced was the same  as Postman's.

Watch out for the correct date to input, as one second difference will generate a different signature.
