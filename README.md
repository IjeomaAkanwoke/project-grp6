# project-grp6
provider "aws" {
  region     = "us-east-1"
  access_key = "AKIAY3C5G3PHJEHXJDML"
  secret_key = "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"
}

resource "aws_s3_bucket" "pdf-bucket" {
  bucket = "kwin-tf-test-bucket-321"

  tags = {
    Name        = "My bucket"
    Environment = "Dev"
  }
}

resource "aws_vpc" "main-vpc" {
  cidr_block       = "10.0.0.0/16"
  
  instance_tenancy = "default"
  enable_dns_hostnames = true

  tags = {
    Name = "main"
  }
}