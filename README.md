# Eth-security-toolbox-ci

This is a fork of trailofbits' [eth-security-toolbox](https://github.com/trailofbits/eth-security-toolbox), which fits the bill for an image to run CI of solidity projects almost perfectly.

However, github runners assume everything will run as the root user, which is not compatible with the aforementioned image using a non-root user, and trying to use it as-is causes runs to fail with various filesystem permission errors.

This image configures what is normally available upstream, using only the root user.

### What image label should I use?

- `latest` if you want the very bleeding edge of whatever we built last.
- Latest pushed tagged version `vx.y.z` if you want an image that wont change in the future.
- `dev` if you want the latest version of this image that went through code review.

### This image has outdated tools 😭 what do?

Simply go to the repository's actions tab and manually run the 'Docker' workflow, which will create a new image pulling the latest version of every tool. Before clicking that button though, consider the following checklist:

- [ ] I verified none of the installed tools (see Dockerfile for updated list) have been compromised at their latest version.
- [ ] I am aware that I'll overwrite the `latest` and `$BRANCH-I-CHOSE-FOR-WORKFLOW` labels for the image in the github container registry, which might affect existing workflows using this image
