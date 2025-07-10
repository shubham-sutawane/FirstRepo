1. Create a Build project under AWS CodeBuild
   --> Select GitHub as source provider
   --> Add github credentions using an AWS managed GitHub App
   -->![image](https://github.com/user-attachments/assets/25740b22-2c4e-4253-bf0d-6390ccb200a5)
   --> Use buildspec file 
   --> Select S3 and bucket for artifact
   
2. Create a deployment under AWS CodeDeploy
   --> Create application using EC2 as compute platform
   --> Create deployment group
      --> Create & attach service role for CodeDeploy to access EC2 and S3 with below policies
           AmazonEC2FullAccess
           AmazonEC2RoleforAWSCodeDeploy
           AmazonEC2RoleforAWSCodeDeployLimited
           AmazonS3FullAccess
           AWSCodeDeployFullAccess
           AWSCodeDeployRole
      --> Create EC2 instance with ubuntu os and add it to DG.
