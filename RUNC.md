containerd is built with OCI support and with support for advanced features provided by `runc`.

We depend on a specific runc version when dealing with advanced features.  You should have a specific build for development.  The current supported runc commit is:

RUNC_COMMIT = e775f0fba3ea329b8b766451c892c41a3d49594d

## building

### apparmor

```bash
make BUILDTAGS='seccomp apparmor' && sudo make install
```

### selinux

```bash
make BUILDTAGS='seccomp selinux' && sudo make install
```

After an official runc release we will start pinning containerd support to a specific version but various development and testing features may require a newer runc version than the latest release.  If you encounter any runtime errors, please make sure your runc is in sync with the commit/tag provided in this document.
