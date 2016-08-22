# TLV Infrastructure for user data

The aim of this infrastructure is provide an easy way to store sequentially user
data into nft kernel objects. It provides functions that allow to create a
buffer of TLV (Type-Len-Value).

The structures looks like this:

```c
/*
 * TLV structures:
 * nftnl_udata
 *  <-------- HEADER --------> <------ PAYLOAD ------>
 * +------------+-------------+- - - - - - - - - - - -+
 * |    type    |     len     |         value         |
 * |  (1 byte)  |   (1 byte)  |                       |
 * +--------------------------+- - - - - - - - - - - -+
 *  <-- sizeof(nftnl_udata) -> <-- nftnl_udata->len -->
 */
struct nftnl_udata {
        uint8_t         type;
        uint8_t         len;
        unsigned char   value[];
} __attribute__((__packed__));

/*
 *              +---------------------------------++
 *              | data[]                          ||
 *              |   ||                            ||
 *              |   \/                            \/
 *  +-------+-------+-------+-------+ ... +-------+- - - - - - -+
 *  | size  |  end  |  TLV  |  TLV  |     |  TLV  |    Empty    |
 *  +-------+-------+-------+-------+ ... +-------+- - - - - - -+
 *                  |<---- nftnl_udata_len() ---->|
 *                  |<----------- nftnl_udata_size() ---------->|
 */
struct nftnl_udata_buf {
        uint32_t        size;
        char            *end;
        char            data[];
};
```

And here is and example of use:

```c
struct nftnl_udata_buf *buf;
struct nftnl_udata *attr;
const char *str = "Hello World!";

buf = nftnl_udata_buf_alloc(UDATA_SIZE);
if (!buf) {
        perror("OOM");
        exit(EXIT_FAILURE);
}

if (!nftnl_udata_put_strz(buf, MY_TYPE, str)) {
        perror("Can't put attribute \"%s\"", str);
        exit(EXIT_FAILURE);
}

nftnl_udata_for_each(buf, attr)
        printf("%s\n", (char *)nftnl_udata_attr_value(attr));

nftnl_udata_buf_free(buf);
```

## Commits
### [nftables](http://netfilter.org/projects/nftables/index.html "nftables project page")

* [set_elem: Use libnftnl/udata to store set element comment                    ](https://git.netfilter.org/nftables/commit/?id=61f851beda31aa3a7dcd4ef534d91b5cfb13594b)
* [netlink_linearize: do not duplicate user data when linearizing user data     ](https://git.netfilter.org/nftables/commit/?id=8979727084d90e6061c8d0f562f8f12e784a657d)
* [rule: Use libnftnl user data TLV infrastructure                              ](https://git.netfilter.org/nftables/commit/?id=795d88cb710512d9b85afbb17beaeec3d92dcd54)

### [libnftnl](http://netfilter.org/projects/libnftnl/index.html "libnftnl project page")

* [tests: Check set user data                                                   ](https://git.netfilter.org/libnftnl/commit/?id=8a593d1cf97a90e750b53f4387ef19da8d7fc574)
* [set: Add new attribute into 'set' to store user data                         ](https://git.netfilter.org/libnftnl/commit/?id=352a74d4e93e3db7380197720eb1003365a5781d)
* [set_elem: Copy user data memory                                              ](https://git.netfilter.org/libnftnl/commit/?id=c326bce873df8fac60c4e8ba8508607f82bb5827)
* [set_elem: Fix memory leak                                                    ](https://git.netfilter.org/libnftnl/commit/?id=88529a7ea173921efa15671b971655da5002ade1)
* [rule: Fix segfault due to invalid free of rule user data                     ](https://git.netfilter.org/libnftnl/commit/?id=0edd209705bc4cf9d2a9e17084310c02d81f4d64)
* [tests: Free nftnl_udata_buf before exit                                      ](https://git.netfilter.org/libnftnl/commit/?id=e4e00c94a2591ef5367d559a4087dde3071e7833)
* [tests: nft-rule-test: check for NFTNL_RULE_USERDATA                          ](https://git.netfilter.org/libnftnl/commit/?id=9552d6cebd050796d2255ad387529f1f22032add)
* [udata: add TLV user data infrastructure                                      ](https://git.netfilter.org/libnftnl/commit/?id=5c3bc232dc9d1dd01d589fab096f67d944621fc2)

### [kernel](https://git.kernel.org/cgit/linux/kernel/git/torvalds/linux.git "linux kernel cgit page")

* [netfilter: nf_tables: Add new attributes into nft_set to store user data.    ](https://git.kernel.org/cgit/linux/kernel/git/torvalds/linux.git/commit/?id=e6d8ecac9e68265aee9be711c5bd29406129666f)
