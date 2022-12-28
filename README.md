# Deploy a high-availability web app using CloudFormation

> ### Diagram

![Diagram](/docs/Project_2_Udacity_CDE_nanodegree.png)

1. You need to create a Secure KeyPair that will use to connect to Bastion Host, in a terminal using the file `utils/create-secure-key.sh`

   > `utils/create-secure-key.sh`

2. You need to create the website files to upload to S3 Bucket, in a terminal using the command zip,

   > `zip udacity.zip src/*`

3. You need to create the s3 and iam stacks, in a terminal using the file `utils/create-stack-key.sh`

   > `utils/create-stack.sh iam-stack iam/iam-stack-template.yml iam/iam-parameters.json`

   > `utils/create-stack.sh s3-stack bucket/s3-bucket-stack-template.yml bucket/s3-bucket-parameters.json`

4. You need to upload the website files created previously to s3 bucket, in a terminal using aws cli

   > `aws s3 cp udacity.zip s3://udagram-s3-store`

5. You need to create the other stacks described above, in a terminal

   > `utils/create-stack.sh network-stack network/network-stack-template.yml network/network-parameters.json`

   > `utils/create-stack.sh bastion-stack bastion/bastion-stack-template.yml bastion/bastion-parameters.json`

   > `utils/create-stack.sh server-stack server/server-stack-template.yml server/server-parameters.json`
