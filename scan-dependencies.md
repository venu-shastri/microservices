#  Microservices Security Design Patterns

## Scan Dependencies
Many of the libraries we use to develop software depend on other libraries. Transitive dependencies lead to a (sometimes) large chain of dependencies, some of which might have security vulnerabilities.
 Use a scanning program on your source code repository to identify vulnerable dependencies. You should scan for vulnerabilities in your deployment pipeline, in your primary line of code, in released versions of code, and in new code contributions.



<!--stackedit_data:
eyJoaXN0b3J5IjpbMzkxMTUxMDA3LC0xOTU4NTU3OTU2XX0=
-->