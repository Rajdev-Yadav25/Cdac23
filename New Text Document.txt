import boto3

s3 = boto3.client('s3')

def lambda_handler(event, context):
    # Get the S3 bucket and key of the uploaded object
    bucket = event['Records'][0]['s3']['bucket']['name']
    key = event['Records'][0]['s3']['object']['key']

    # Print the bucket and key of the uploaded object
    print("Object {} was uploaded to bucket {}".format(key, bucket))