# rust-cicd


## Running a Registry

1. A minimal registry can be implemented by having a git repository that contains an index, and a server that contains the compressed .crate files created by cargo package. Users won't be able to use Cargo to **publish** to it, but this may be sufficient for closed environments.


2. A full-featured registry that supports publishing will additionally need to have a web API service that conforms to the API used by Cargo. The web API is documented below.
Commercial and community projects are available for building and running a registry. See https://github.com/rust-lang/cargo/wiki/Third-party-registries for a list of what is available.

* [Cloudsmith](https://cloudsmith.com)
* [JFrog](https://jfrog.com/integration/cargo-registry/)
* [Private Crates.io](https://github.com/rust-lang/crates.io) (not a really good idea) 



### Using a Git repository as a private Cargo registry

Another approach to installing a private Cargo registry is to configure a Git repository to serve as a Cargo registry. Under this strategy (which is explained in more detail in this blog post), you host your Cargo packages in a Git repo, and pull them from there in a fashion that is similar in most ways to the process you’d use with a registry like crates.io.

To do this, you’ll first need a Git repository. You can set that up on your own server, or by using a hosted service like GitHub.

