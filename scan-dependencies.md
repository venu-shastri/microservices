#  Microservices Security Design Patterns

## Scan Dependencies
Many of the libraries we use to develop software depend on other libraries. Transitive dependencies lead to a (sometimes) large chain of dependencies, some of which might have security vulnerabilities.
 Use a scanning program on your source code repository to identify vulnerable dependencies. You should scan for vulnerabilities in your deployment pipeline, in your primary line of code, in released versions of code, and in new code contributions.

 - GitHub user,  use [dependabot](https://dependabot.com/) to provide automated updates via pull requests
 - [https://snyk.io/](https://snyk.io/)
 - [https://jfrog.com/xray/](https://jfrog.com/xray/)

<!--stackedit_data:
eyJoaXN0b3J5IjpbMTM1NTY0ODEyOCwzOTExNTEwMDcsLTE5NT
g1NTc5NTZdfQ==
-->