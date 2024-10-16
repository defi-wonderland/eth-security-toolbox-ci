# eth-security-toolbox-ci

this is a fork of trailofbits' [eth-security-toolbox](https://github.com/trailofbits/eth-security-toolbox), which fits the bill for an image to run CI of solidity projects almost perfectly.

However, github runners assume everything will run as the root user, which is not compatible with the aforementioned image using a non-root user, and trying to use it as-is causes runs to fail with various filesystem permission errors.

This image configures what is normally available upstream, using only the root user
