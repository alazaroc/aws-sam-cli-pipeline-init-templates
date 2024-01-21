# My custom SAM pipeline template with a one-stage

This is a fork of the AWS repository: <https://github.com/aws/aws-sam-cli-pipeline-init-templates>

When you execute `sam pipeline init` you can choose the following:

> Select a pipeline template to get started:
> 1 - AWS Quick Start Pipeline Templates
> 2 - Custom Pipeline Template Location

However, option 1 creates a pipeline with 2 stages, and **I want to create only one stage**, so I forked the original repository and created my custom template.

To work with the AWS CLI `sam pipeline init` with the custom template option (2), I had to clean the project and leave in the main folder the specific template to execute. I don't know why it didn't work with the full repository... AWS people, why? :)

In this post that I wrote in my blog, I explained how to use this template to create a CI/CD pipeline with AWS CodePipeline: <https://www.playingaws.com/posts/how-to-add-ci-cd-to-my-sam-project/>

I have also made some changes to the parameters section to customize it more.

List of changes:
- (new): codepipeline_s3_artifact - I wanted to be able to specify a custom bucket for my pipeline. However, we already had one... this bucket is only for the CodePipeline artifacts. Now, there are 2 buckets: one for the SAM deployments and the other for the CodePipeline artifacts
- (new) testing_artifacts_bucket_prefix_sam: I wanted to specify the prefix of my s3 bucket...
- (updated) CodeBuild buildspec_build_package.yml: Why I should use a container to build my application? It is time-consuming and you can do it directly...

Please, if you like it, leave me a comment in my blog post <https://www.playingaws.com/posts/how-to-add-ci-cd-to-my-sam-project/>
