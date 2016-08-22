# Rule deletion by description

This patch introduces deletion in a similar fashion as in iptables, thus,
we can delete the first rule that matches our description, for example:

```bash
$ nft list -a ruleset
table ip t {
    chain c {
	    ip saddr 1.1.1.1 counter packets 0 bytes 0 # handle 1
	    ip saddr 1.1.1.2 counter packets 0 bytes 0 # handle 2
	    ip saddr 1.1.1.2 counter packets 0 bytes 0 # handle 3
	    ip saddr 1.1.1.4 counter packets 0 bytes 0 # handle 4
    }
}
$ nft delete rule table chain ip saddr 1.1.1.2 counter
$ nft list -a ruleset
table ip t {
    chain c {
	    ip saddr 1.1.1.1 counter packets 0 bytes 0 # handle 1
	    ip saddr 1.1.1.2 counter packets 0 bytes 0 # handle 3
	    ip saddr 1.1.1.4 counter packets 0 bytes 0 # handle 4
    }
}
```

For archive this I have needed to introduce several changes into libnftnl
library. I have implemented comparators for rule and expression objects.

**NOTE:** I have some patches that must be accepted before I can consider the
work completed.

## Commits
### [nftables](http://netfilter.org/projects/nftables/index.html "nftables project page")

* *PENDING APPOVAL* [parser: Improve syntax errors                              ](https://github.com/FarK/nf-nftables/commit/842c89d3ddda78d2c4e3e241f07264a780fe53f8)
* *PENDING APPOVAL* [test: shell: Add tests for deleting rule by description    ](https://github.com/FarK/nf-nftables/commit/ed007e53d5f9adc91d65f61900770f1cb62a5f12)
* *PENDING APPOVAL* [Implement deleting rule by description                     ](https://github.com/FarK/nf-nftables/commit/d6b4900e32de3aa2c319b975770e9412c8ad2bec)
* *PENDING APPOVAL* [Simplify parser rule_spec tree                             ](https://github.com/FarK/nf-nftables/commit/1165ea95d8efe191fcc5bab075219e512c371eb8)

### [libnftnl](http://netfilter.org/projects/libnftnl/index.html "libnftnl project page")

* [rule: Fix comparison between rules if number of expressions differ           ](https://git.netfilter.org/libnftnl/commit/?id=0cbe60118eafe734de7369783cf1c92f6e0934f1)
* [src: Implement rule comparison                                               ](https://git.netfilter.org/libnftnl/commit/?id=e35693fd13de771e1e047ffa4f799f72f1446e8d)
* [rule: Implement internal iterator for expressions                            ](https://git.netfilter.org/libnftnl/commit/?id=94ccd4e72d3dfff000d8212ae63f45cd950bb53b)
* [src: Constify iterators                                                      ](https://git.netfilter.org/libnftnl/commit/?id=b02d5d5b766e30a2afcbb706aa69ea7a51b40bc8)
