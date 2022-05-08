#

## ch1

https://book.mynavi.jp/files/user/support/9784839962135/mondai1

### mondai1

`file ./mondai1/SelfReference`

```s
./mondai1/SelfReference: ELF 32-bit LSB executable, Intel 80386, version 1 (SYSV), dynamically linked, interpreter /lib/ld-linux.so.2, for GNU/Linux 2.6.32, BuildID[sha1]=2eab3d3c43485546624750fefbf0ac345054105b, stripped
```

`strings ./mondai1/SelfReference`

```s
/lib/ld-linux.so.2
=<CHUFbGP
libc.so.6
_IO_stdin_used
exit
srand
fopen
strncpy
puts
__stack_chk_fail
putchar
printf
fgets
calloc
strlen
fseek
strcmp
__libc_start_main
free
__gmon_start__
GLIBC_2.1
GLIBC_2.4
GLIBC_2.0
PTRh
QVhY
UWVS
t$,U
[^_]
-encrypt
plain            : %s
encrypted(hex)   :
%02x
-decrypt
[-] This option is implemented.
Invalid option.
Usage :
  ./SelfReference -encrypt <str>
--------------------------------
FLAG{
FLAG (encrypted)(hex)    :
[-] Decrypt function is implemented.
;*2$"
GCC: (Ubuntu 5.4.0-6ubuntu1~16.04.4) 5.4.0 20160609
.shstrtab
.interp
.note.ABI-tag
.note.gnu.build-id
.gnu.hash
.dynsym
.dynstr
.gnu.version
.gnu.version_r
.rel.dyn
.rel.plt
.init
.plt.got
.text
.fini
.rodata
.eh_frame_hdr
.eh_frame
.init_array
.fini_array
.jcr
.dynamic
.got.plt
.data
.bss
.comment
XV5xxMLwKP8KaayCSG04vQVv0kMSA3ZTRyZ4bCyet8VXaceow53CkC3JA0ZAg5wBx86kHvlCYhdeVPSCeEYy3rFVyOJdZTNgwxSgcRYZV6E28DqXMm5aYnfm3Z4uEDUz1FpmneQcuwOPwrMdx9Gy4Q3MKZIaalSHHKvpuQn5zbTtmgPfwpWVMSnuP0fV43mfuPQGX6ryJk2ANuuXxctZ03CNj5U6wF3X2cor5baXfZzFRltlMM5cl8BHAptzDkPMYFBWUg56usLpnq9gawM0XWMOIbx8z99logD8nCzj4QsjHAsnWf1EfrGZs1JCyF8fsHKzSWXUp8QWLUfgtPWWwI6ae3f5eEE9eqKAAqqp8s05HMAnEltRpFAe5jq25LW71BdnMVlP8p9EkD3ICugWJzZSo2saKenlJiMa7kOvCVc1qPAvEl0G2Txv79FSK2req4wpfoEv9u5ZwzqrSn2n8z3e8T3SfbzwKFDvr5Izhh1Ndt6w91CNqwGWwdDzb3VpAU7yn9RJrTWTZKKYc21WmKaetofqNwSYFPT4jdl3bM6Fe0NFClMqXcuC1LnCeVWy1OVvDUGw8g7lqO6Sfa9flHv0HkBt5WwANXpS1ddDQONQTSt4keGlBYAq9bzBBTKO9gy3agaT2GmKWt6rYacOM2kFq9rjWaZgSrhjxCOMO83jOixVfyEIQwDF5LUNc679WWtTFk0LLLYXuP1iZwnqs0PXrXwaqtfGO4GuqiU9ciDpBTHbxCql4WLrbMSSpqVvAmazvOAJnFvmcIdBfp7fZEd16i6h47IW7wPquyWQL5x9ePrJWZx6skvq2Gt0AcPBMMg5bSYGvcN43g34UjFmAuj9WDITQ6Z6bde8grMMpyyAJYQwr4ycZJN0vaJp9WGr6DaZB98THfQPhgiRvOGW3GLT03HgnR3kZXW0zt38b790Uvkj7yjAAX6ItBQb0zMt95hK8eyPkP1cgHSapReU2G6I6UJjQ0pFUgHfpK6pmkmJbrinid5WqgImMunLrwR0
```

`./SelfReerrence`

```
Usage :
  ./SelfReference -encrypt <str>

--------------------------------

FLAG{
[-] Decrypt function is implemented.
FLAG (encrypted)(hex)    : 7d 56 18 43 15 67 0f 0a 1c 28 3b 76 05 30 00 50 54 0c 59 09 1f 7d 0d 3a 02 7a 08 7e 01 40 57 60 11 3e 05 2d 05 0f 00 00 06 55 30
}
```

`r2 ./SelfReference`

```sh
[0x080485f0]> aa
[x] Analyze all flags starting with sym. and entry0 (aa)
[0x080485f0]> aac
[0x080485f0]> afl
0x080485f0    1 33           entry0
0x08048580    1 6            sym.imp.__libc_start_main
0x080484e0    1 6            sym.imp.strcmp
0x080484f0    1 6            sym.imp.printf
0x08048500    1 6            sym.imp.free
0x08048510    1 6            sym.imp.fgets
0x08048520    1 6            sym.imp.__stack_chk_fail
0x08048530    1 6            sym.imp.fseek
0x08048540    1 6            sym.imp.puts
```