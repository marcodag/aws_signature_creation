# aws_signature_creation
this repo contains the generic Java algorithm to create AWS signature for accessing s3 private buckets.

The algorithm was tested OK for retrieving (GET) an object from an s3 private bucket, without any query parameters, following https://docs.aws.amazon.com/AmazonS3/latest/API/sig-v4-header-based-auth.html guidelines.
The right signature's output was tested by doing the call on Postman, with AWS headers. The call created an Authorization header that contained the signature.
Then, from the the X-Amz-Date header, the signature was created by the Java algorithm, which produced the same signature as Postman did.
