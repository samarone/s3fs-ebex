# s3fs-ebex
Template for mount s3 into environment AWS Elastic Beanstalk using s3fs and ebextensions


Configuration
--------
You should replace the variables with your aprropiate values inside .ebextensions/01-s3fs-ebex.config, example:

* $BASE_DIR$=/usr/share/tomcat8
* $MOUNT_DIR$=/usr/share/tomcat8/bucket
* $BUCKET_NAME$=``<bucketName>``
* $BUCKET_CREDENTIALS$=``<bucketName>:<accessKeyId>:<secretAccessKey>``
* $UID$=``<userId>`` , set 0 for root
* $GID$=``<groupId>`` , set 0 for root


Example of AIM Policy for use:
--------

``{
    "Version": "2012-10-17",
    "Statement": [
        {
            "Effect": "Allow",
            "Action": "s3:*",
            "Resource": [
                "arn:aws:s3:::<bucketName>/*"
            ]
        }
    ]
}``
