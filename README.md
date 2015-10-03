# cloudformation-templates

Cloudformation templates for creating a coreos instance using shared stack resources on aws

## Usage

If you have not added any EC2 keys go to EC2 keypairs and add a new keypair.

Create a stack using `lambda_role.template`, make a note of the arn in output.

Create a stack using `lambda_function.template` using  the arn from `lambda_role.template`, make a note of the arn in output.

Create a stack using `vpc_stack.template`.

Create a stack using `rds_stack.template` using  the arn from `lambda_function.template` and the name of the stack using `vpc_stack.template`.

Create a stack using `instance_stack.template` using  the arn from `lambda_function.template` and the names of the stacks using `vpc_stack.template` and `rds_stack.template`.

Add a EIP (Elastic IP) to the instance and ssh to it using the key added as keypair to the instance.

Run this command using master database, user and password:
```
  docker run --env-file=/django_env -it --rm postgres \
      bash -c 'psql -h $DATABASE_ENDPOINT -p $DATABASE_ENDPOINT_PORT -U masteruser -W'
```

## Contributing

1. Fork it!
2. Create your feature branch: `git checkout -b my-new-feature`
3. Commit your changes: `git commit -am 'Add some feature'`
4. Push to the branch: `git push origin my-new-feature`
5. Submit a pull request :D

## Credits

Øyvind Saltvik
