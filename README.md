# cloudformation-templates

Cloudformation templates for creating a coreos instance using shared stack resources on aws

## Usage

Create a stack using `lambda_role.template`, make a note of the arn in output.

Create a stack using `lambda_function.template` using  the arn from `lambda_role.template`, make a note of the arn in output.

Create a stack using `vpc_stack.template`.

Create a stack using `rds_stack.template` using  the arn from `lambda_function.template` and the name of the stack using `vpc_stack.template`.

Create a stack using `instance_stack.template` using  the arn from `lambda_function.template` and the names of the stacks using `vpc_stack.template` and `rds_stack.template`.

## Contributing

1. Fork it!
2. Create your feature branch: `git checkout -b my-new-feature`
3. Commit your changes: `git commit -am 'Add some feature'`
4. Push to the branch: `git push origin my-new-feature`
5. Submit a pull request :D

## Credits

Øyvind Saltvik
