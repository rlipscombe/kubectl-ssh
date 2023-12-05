# kubectl-ssh

A plugin for kubectl that allows you to SSH to a pod.

## Installation

Put the files from the `bin` directory somewhere in your `$PATH` and make sure
they're executable.

## Usage

```sh
# Connect to a pod in the current namespace.
kubectl ssh POD
```

```sh
# Connect to an arbitrary pod in the named deployment.
kubectl -n NAMESPACE ssh deployment/DEPLOYMENT
```

## Tab Completion

Tab completion for `kubectl ssh` works, provided you've got `kubectl` newer than
`v1.26.0`, and that tab completion for `kubectl` works for other commands.

## Troubleshooting

The pod you're trying to connect to _is_ running an SSH daemon, right? This is
not magic, and won't work if it's not.

## Caution

Note that the SSH connection goes via the Kubernetes API server, so don't do
anything too involved.

For example: don't run `rsync` over the connection or anything.

## Links

See <https://blog.differentpla.net/blog/2023/02/28/kubectl-ssh-plugin/>.
