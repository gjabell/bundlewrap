# FAQ

## Technical

### BundleWrap says an item failed to apply, what do I do now?

Try running `bw apply -i nodename` to see which attribute of the item could not be fixed. If that doesn't tell you enough, try `bw --debug apply -i nodename` and look for the command BundleWrap is using to fix the item in question. Then try running that command yourself and check for any errors.

<br>

### What happens when two people start applying configuration to the same node?

BundleWrap uses a [locking mechanism](../guide/locks.md) to prevent collisions like this.

<br>

### How can I have BundleWrap reload my services after config changes?

See [canned actions](../repo/bundles.md#canned_actions) and [triggers](../repo/bundles.md#triggers).

<br>

### Will BundleWrap keep track of package updates?

No. BundleWrap will only care about whether a package is installed or not. Updates will have to be installed through a separate mechanism (I like to create an [action](../items/action.md) with the `interactive` attribute set to `True`). Selecting specific versions should be done through your package manager.

<br>

### Is there a probing mechanism like Ohai?

No. BundleWrap is meant to be very push-focused. The node should not have any say in what configuration it will receive.

<br>

### Is there a way to remove any unmanaged files/directories in a directory?

Not at the moment. We're tracking this topic in issue [#56](https://github.com/bundlewrap/bundlewrap/issues/56).

<br>

### Is BundleWrap secure?

BundleWrap is more concerned with safety than security. Due to its design, it is possible for your coworkers to introduce malicious code into a BundleWrap repository that could compromise your machine. You should only use trusted repositories and plugins. We also recommend following commit logs to your repos.

<br>

## The BundleWrap Project

### Why do contributors have to sign a Copyright Assignment Agreement?

While it sounds scary, Copyright assignment is used to improve the enforceability of the GPL. Even the FSF does it, [read their explanation why](http://www.gnu.org/licenses/why-assign.html). The agreement used by BundleWrap is from [harmonyagreements.org](http://harmonyagreements.org).

If you're still concerned, please do not hesitate to contact [@trehn](https://twitter.com/trehn).

<br>

### Isn't this all very similar to Ansible?

Some parts are, but there are significant differences as well. Check out the [alternatives page](alternatives.md#ansible) for a writeup of the details.

<br>