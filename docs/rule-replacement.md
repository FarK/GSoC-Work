# Rule Replacement

Modify the parser and add necessary functions to provide the command "nft
replace rule &lt;ruleid_spec&gt; &lt;new_rule&gt;"

Example of use:

```bash
$ nft list ruleset -a
table ip filter {
    chain output {
	    ip daddr 8.8.8.7 counter packets 0 bytes 0 # handle 3
    }
}
$ nft replace rule filter output handle 3 ip daddr 8.8.8.8 counter
$ nft list ruleset -a
table ip filter {
    chain output {
	    ip daddr 8.8.8.8 counter packets 0 bytes 0 # handle 3
    }
}
```

## Commits
* [src: Add command "replace" for rules](https://git.netfilter.org/nftables/commit/?id=0721fbbe7a951a1e879d120c7a722012c38af9a6)
