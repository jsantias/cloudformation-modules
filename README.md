# CloudFormation modules

A collection of modules that can be reused for creating AWS infrastructure. This can be reused as many times as you want and instead of having to reinvent the wheel. It also falls into AWS's best practices for creating modular templates. The collection here covers all of the AWS services I have worked with however may require tweaking to suit your own needs.

## How to use a module

1. Upload any of the templates into an S3 bucket. Take note of the object URL

2. Create a CloudFormation template that will reference the S3 object. Example, using the `aws-glue/glue-database.yml` module:

   ```
   GlueDatabase:
       Type: AWS::CloudFormation::Stack
       Properties:
         TemplateURL: https://<bucket-name>.s3.<region>.amazonaws.com/modules/glue-table.yml
         Parameters:
           GlueDBName: 'my-glue-db'
   ```

3. Deploy!

## Contributing

Project is open to people who would like to contribute. To contribute:

1. Fork the repository
2. Make your changes to a branch
3. Create a Pull Request to this repository