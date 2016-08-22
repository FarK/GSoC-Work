# Fixes

Along my work at Google Summer of Code I have found and fixed several bugs in
nftables and libnftnl. Here is a list of these commits:

## [nftables](http://netfilter.org/projects/nftables/index.html "nftables project page")

* [parser: cap comment length to 128 bytes                                      ](https://git.netfilter.org/nftables/commit/?id=aef75641d196ddc199df35092823f178b998a6a3)
* [parser: Consolidate comment production                                       ](https://git.netfilter.org/nftables/commit/?id=ab88635f6f71fbacdbcba05e70058d31e70bcd66)

## [libnftnl](http://netfilter.org/projects/libnftnl/index.html "libnftnl project page")

* [expr: cmp: Use cmp2str() instead of directly access to array                 ](https://git.netfilter.org/libnftnl/commit/?id=af494b6878ed605e3b52d13e6aba023f3cd985ca)
* [utils: Fix out of bound access in nftnl_family2str                           ](https://git.netfilter.org/libnftnl/commit/?id=77d244245c5b923b4cc8c88c9ad99291f6bba4c1)
* [tests: masq: Fix wrong expression creation                                   ](https://git.netfilter.org/libnftnl/commit/?id=d9f68d62681fba81e0fe428647ae3a7a0ce659c0)
* [tests: Fix tests for immediate and lookup expressions                        ](https://git.netfilter.org/libnftnl/commit/?id=8f003ead750d947cb1ba1c3bc2db44c318a001d2)
* [expr: Fix lookup builder                                                     ](https://git.netfilter.org/libnftnl/commit/?id=4525b501a3c6b3b82422467f664e9430628dd770)
* [src: Fix nftnl_*_get_data() to return the real attribute length              ](https://git.netfilter.org/libnftnl/commit/?id=bda7102d60bfdab2aa3f36ebd09a119206f264d0)
* [src: Fix missing nul-termination in nftnl_*_set_str()                        ](https://git.netfilter.org/libnftnl/commit/?id=8f1e916b9856785cb835a2d550c9605e86937055)
* [src: fix missing error checking in parser functions                          ](https://git.netfilter.org/libnftnl/commit/?id=59cb13bb62b36efa25b29fe280ada7b1f0984325)
* [chain: Check correct attribute                                               ](https://git.netfilter.org/libnftnl/commit/?id=2fee091b0dd1741a8a87cafceaa0091adadd2b46)
* [src: Fix leak in nftnl_*_unset()                                             ](https://git.netfilter.org/libnftnl/commit/?id=396cdb2375af8c8b8884f5f50c773a39b29a06d7)
* [src: fix memory leaks at nft_[object]_nlmsg_parse                            ](https://git.netfilter.org/libnftnl/commit/?id=6e188637782c6c62c7bcade808e59d17639d677d)
