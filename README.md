# crab-eye
A recursive file watcher written in Rust, similar to watchman but better

Not yet built. The idea is that it loops through subdirectories using a regex and then also excludes files using a regex. Inotify is ONLY used if a file is updated and only about 100 files or so are watched under inotify so as not to exhaust the open file handles.

The motivation for writing this is that watchman seems to break in some circumstances, such as running under docker. It's also not well documented and requires a service to run. The use of regex is to use a standard language for defining a path, and glob is not used so that it is intelligent.
