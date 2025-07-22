Created: 20250622

Rust allows you to build documentation <ul>locally</ul> for all dependencies
used by your project, and store them in ./target/doc/<project-name>/index.html.

To utilize this, run

    cargo doc --open

in the root of your project.

(Unsure if it needs to be run in root, but better safe than sorry)
