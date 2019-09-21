# First install terraform for Lnux and VMware, gcc, aws, azure

terraform -install-autocomplete

## download examples
https://github.com/kevholditch/terraform-course-examples

git clone git@github.com:ricardo-rod/terraform-course-examples.git

# export the keys or apis ans users to use with vmware

    - create a new user on amazon or gcc or provider your preference
    - create a new user on AWS IAM programmatic user, and add attache setting
    and full access to aws.
    - copy everything, download the cvs


$ export AWS_ACCESS_KEY_ID="anaccesskey"
$ export AWS_SECRET_ACCESS_KEY="asecretkey"
$ export AWS_DEFAULT_REGION="us-east-2"


export AWS_ACCESS_KEY_ID=XXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXX
export AWS_SECRET_ACCESS_KEY=XXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXX

vim ~/.bashrc
printenv | grep AWS

# run as user

terraform init

terraform apply

terraform destroy


# -----------------------------------------------------------------------------
#

Terraformn Cocepts

Resources

Data sources

Locals

Outputs

Templates and files = setup sort complex, as configuration for ex: docker

Provider

Variables: dynamicly input data just for apply and run


# -----------------------------------------------------------------------------
# Terraform Resources
https://www.terraform.io/docs/providers/index.html

https://www.terraform.io/docs/providers/aws/index.html

The Amazon Web Services (AWS) provider is used to interact with the many
resources supported by AWS. The provider needs to be configured with the
proper credentials before it can be used.

Use the navigation to the left to read about the available resources.

Resources are component of our infrastructure. They might be a low
level componen line a physical server, vm, or container o they could be
a higher level componen like a DNS record or email provider.

- Resourse arguments & exported attributes
 - Resources have a set of arguments
    - required
    - optional
 - Resources can have exported attributes

resource "aws_s3_bucket" "my_zoe_bucket" {
  bucket = "zoezoezoe-myfirst-bucket"
}

 - The aws_s3 bucket returns the ARN created as one of its exported attributes


- Interpolation syntax
Helps Terraform work out dependency order

for example:

resource "aws_s3_bucket" "my_zoe_bucket" {
  bucket = "zoezoezoe-myfirst-bucket"
}

"${aws_s3_bucket.my_zoe_bucket.arn}"


# Data types
- 4 main data types for resources attributes

    Int - defined using - port = 21
    String - defined using = host = "localhost"
    List - Defined using - security_groups = ["abc", "def"]
_
    Bool - defined using - enabled = false



# -----------------------------------------------------------------------------
#

