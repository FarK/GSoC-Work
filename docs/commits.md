# List of my commits

Here is a list of my commits to the Netfilter project sorted by repository.
You can click a commit title to open its diff and description.

# [nftables](http://netfilter.org/projects/nftables/index.html "nftables project page")

* *PENDING APPOVAL* [parser: Improve syntax errors                              ](https://github.com/FarK/nf-nftables/commit/842c89d3ddda78d2c4e3e241f07264a780fe53f8)
* *PENDING APPOVAL* [test: shell: Add tests for deleting rule by description    ](https://github.com/FarK/nf-nftables/commit/ed007e53d5f9adc91d65f61900770f1cb62a5f12)
* *PENDING APPOVAL* [Implement deleting rule by description                     ](https://github.com/FarK/nf-nftables/commit/d6b4900e32de3aa2c319b975770e9412c8ad2bec)
* [Simplify parser rule_spec tree                                               ](https://git.netfilter.org/nftables/commit/cec8dde7af3ec0f2e16d6445b14f77a2c357221e)
* [parser: cap comment length to 128 bytes                                      ](https://git.netfilter.org/nftables/commit/?id=aef75641d196ddc199df35092823f178b998a6a3)
* [parser: Consolidate comment production                                       ](https://git.netfilter.org/nftables/commit/?id=ab88635f6f71fbacdbcba05e70058d31e70bcd66)
* [set_elem: Use libnftnl/udata to store set element comment                    ](https://git.netfilter.org/nftables/commit/?id=61f851beda31aa3a7dcd4ef534d91b5cfb13594b)
* [netlink_linearize: do not duplicate user data when linearizing user data     ](https://git.netfilter.org/nftables/commit/?id=8979727084d90e6061c8d0f562f8f12e784a657d)
* [rule: Use libnftnl user data TLV infrastructure                              ](https://git.netfilter.org/nftables/commit/?id=795d88cb710512d9b85afbb17beaeec3d92dcd54)
* [src: Add command "replace" for rules                                         ](https://git.netfilter.org/nftables/commit/?id=0721fbbe7a951a1e879d120c7a722012c38af9a6)

# [libnftnl](http://netfilter.org/projects/libnftnl/index.html "libnftnl project page")

* [rule: Fix comparison between rules if number of expressions differ           ](https://git.netfilter.org/libnftnl/commit/?id=0cbe60118eafe734de7369783cf1c92f6e0934f1)
* [src: Implement rule comparison                                               ](https://git.netfilter.org/libnftnl/commit/?id=e35693fd13de771e1e047ffa4f799f72f1446e8d)
* [expr: cmp: Use cmp2str() instead of directly access to array                 ](https://git.netfilter.org/libnftnl/commit/?id=af494b6878ed605e3b52d13e6aba023f3cd985ca)
* [utils: Fix out of bound access in nftnl_family2str                           ](https://git.netfilter.org/libnftnl/commit/?id=77d244245c5b923b4cc8c88c9ad99291f6bba4c1)
* [tests: masq: Fix wrong expression creation                                   ](https://git.netfilter.org/libnftnl/commit/?id=d9f68d62681fba81e0fe428647ae3a7a0ce659c0)
* [tests: Fix tests for immediate and lookup expressions                        ](https://git.netfilter.org/libnftnl/commit/?id=8f003ead750d947cb1ba1c3bc2db44c318a001d2)
* [expr: Fix lookup builder                                                     ](https://git.netfilter.org/libnftnl/commit/?id=4525b501a3c6b3b82422467f664e9430628dd770)
* [tests: Add missing tests to test-script.sh                                   ](https://git.netfilter.org/libnftnl/commit/?id=72d7fa0ebb58efc8a86796f334cfe4b3d38d81ca)
* [rule: Implement internal iterator for expressions                            ](https://git.netfilter.org/libnftnl/commit/?id=94ccd4e72d3dfff000d8212ae63f45cd950bb53b)
* [src: Constify iterators                                                      ](https://git.netfilter.org/libnftnl/commit/?id=b02d5d5b766e30a2afcbb706aa69ea7a51b40bc8)
* [src: Fix nftnl_*_get_data() to return the real attribute length              ](https://git.netfilter.org/libnftnl/commit/?id=bda7102d60bfdab2aa3f36ebd09a119206f264d0)
* [src: Fix missing nul-termination in nftnl_*_set_str()                        ](https://git.netfilter.org/libnftnl/commit/?id=8f1e916b9856785cb835a2d550c9605e86937055)
* [tests: Check set user data                                                   ](https://git.netfilter.org/libnftnl/commit/?id=8a593d1cf97a90e750b53f4387ef19da8d7fc574)
* [set: Add new attribute into 'set' to store user data                         ](https://git.netfilter.org/libnftnl/commit/?id=352a74d4e93e3db7380197720eb1003365a5781d)
* [src: fix missing error checking in parser functions                          ](https://git.netfilter.org/libnftnl/commit/?id=59cb13bb62b36efa25b29fe280ada7b1f0984325)
* [chain: Check correct attribute                                               ](https://git.netfilter.org/libnftnl/commit/?id=2fee091b0dd1741a8a87cafceaa0091adadd2b46)
* [src: Fix leak in nftnl_*_unset()                                             ](https://git.netfilter.org/libnftnl/commit/?id=396cdb2375af8c8b8884f5f50c773a39b29a06d7)
* [set_elem: Copy user data memory                                              ](https://git.netfilter.org/libnftnl/commit/?id=c326bce873df8fac60c4e8ba8508607f82bb5827)
* [set_elem: Fix memory leak                                                    ](https://git.netfilter.org/libnftnl/commit/?id=88529a7ea173921efa15671b971655da5002ade1)
* [rule: Fix segfault due to invalid free of rule user data                     ](https://git.netfilter.org/libnftnl/commit/?id=0edd209705bc4cf9d2a9e17084310c02d81f4d64)
* [tests: Free nftnl_udata_buf before exit                                      ](https://git.netfilter.org/libnftnl/commit/?id=e4e00c94a2591ef5367d559a4087dde3071e7833)
* [libnftnl: gitignore: Fix mistake in gitignore regexp                         ](https://git.netfilter.org/libnftnl/commit/?id=60ad2e781ad14a04b5d8ac3c1736e29ef3f24127)
* [libnftnl: Add to .gitignore all auto-generated files                         ](https://git.netfilter.org/libnftnl/commit/?id=f3d37ef44651b92d99df7e55d2bb08f7aee45e4f)
* [tests: nft-rule-test: check for NFTNL_RULE_USERDATA                          ](https://git.netfilter.org/libnftnl/commit/?id=9552d6cebd050796d2255ad387529f1f22032add)
* [udata: add TLV user data infrastructure                                      ](https://git.netfilter.org/libnftnl/commit/?id=5c3bc232dc9d1dd01d589fab096f67d944621fc2)
* [src: fix memory leaks at nft_[object]_nlmsg_parse                            ](https://git.netfilter.org/libnftnl/commit/?id=6e188637782c6c62c7bcade808e59d17639d677d)

# [libmnl](http://netfilter.org/projects/libmnl/index.html "libmnl project page")

* [nlmsg: Improve payload printing                                              ](https://git.netfilter.org/libmnl/commit/?id=610b1208a4d87b874e55982d44c0a9a1a1b7b00d)

# [kernel](https://git.kernel.org/cgit/linux/kernel/git/torvalds/linux.git "linux kernel cgit page")

* [netfilter: nf_tables: Add new attributes into nft_set to store user data.    ](https://git.kernel.org/cgit/linux/kernel/git/torvalds/linux.git/commit/?id=e6d8ecac9e68265aee9be711c5bd29406129666f)
