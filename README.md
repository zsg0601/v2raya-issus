# v2raya-issus
记录docker部署v2raya的问题

#查询群晖docker运行的mod
lsmod
Module                  Size  Used by
xt_string               1435  0 
ts_bm                   2098  0 
textsearch              2284  2 ts_bm,xt_string
xt_TPROXY               4955  0 
xt_connmark             2043  0 
ip_set_hash_net        22142  0 
xt_set                  8108  0 
ip_set_hash_ip         18317  0 
ip_set                 23799  3 ip_set_hash_net,ip_set_hash_ip,xt_set
nfnetlink               5757  2 ip_set
xfrm_user              23737  1 
xfrm_algo               5501  1 xfrm_user
pci_stub                1613  0 
vfio_pci               28971  0 
vfio_virqfd             2293  1 vfio_pci
vfio_iommu_type1        8325  0 
vfio                   15175  2 vfio_iommu_type1,vfio_pci
vhost_net              10917  0 
kvm_intel             152794  0 
kvm                   434147  1 kvm_intel
irqbypass               2808  2 kvm,vfio_pci
fuse                   87662  1 
xt_ipvs                 2326  0 
ip_vs_rr                1511  0 
ip_vs                 122297  3 ip_vs_rr,xt_ipvs
xt_mark                 1381  0 
iptable_mangle          1720  0 
br_netfilter           13051  0 
bridge                 56231  1 br_netfilter
stp                     1757  1 bridge
aufs                  203566  0 
macvlan                13507  0 
veth                    5094  0 
xt_conntrack            3407  0 
xt_addrtype             3012  0 
nf_conntrack_ipv6       6656  0 
ip6table_filter         1596  1 
ip6_tables             14677  1 ip6table_filter
ipt_MASQUERADE          1341  20 
xt_REDIRECT             1550  0 
nf_nat_masquerade_ipv4     2109  1 ipt_MASQUERADE
xt_nat                  2091  33 
nf_nat_redirect         1395  1 xt_REDIRECT
xt_recent               8685  0 
xt_iprange              1776  0 
xt_limit                2093  0 
xt_state                1539  0 
xt_tcpudp               2607  61 
xt_multiport            1958  0 
xt_LOG                  1551  0 
iptable_filter          1656  1 
iptable_nat             2023  6 
nf_nat_ipv4             4839  1 iptable_nat
nf_nat                 10897  4 nf_nat_redirect,nf_nat_ipv4,xt_nat,nf_nat_masquerade_ipv4
nf_conntrack_ipv4      11666  1 
nf_defrag_ipv4          1539  2 xt_TPROXY,nf_conntrack_ipv4
ip_tables              14150  3 iptable_filter,iptable_mangle,iptable_nat
tun                    19836  5 vhost_net
vfat                   10511  0 
fat                    55795  1 vfat
vhost_scsi             28995  1 
vhost                  30822  2 vhost_net,vhost_scsi
tcm_loop               15357  1 
iscsi_target_mod      272216  1 
target_core_user       27400  0 
target_core_ep         50980  2 
target_core_multi_file    29151  1 
target_core_file       59357  1 
target_core_iblock     17374  1 
target_core_mod       894821  22 target_core_iblock,target_core_multi_file,vhost,iscsi_target_mod,target_core_ep,target_core_file,target_core_user,vhost_scsi,tcm_loop
syno_extent_pool     1385313  0 
rodsp_ep               91947  3 target_core_multi_file,syno_extent_pool,target_core_file
x_tables               17075  23 ip6table_filter,xt_ipvs,xt_iprange,xt_mark,xt_recent,ip_tables,xt_tcpudp,xt_string,ipt_MASQUERADE,xt_limit,xt_state,xt_conntrack,xt_LOG,xt_nat,xt_set,xt_multiport,iptable_filter,xt_TPROXY,xt_connmark,xt_REDIRECT,iptable_mangle,ip6_tables,xt_addrtype
udf                    80886  0 
isofs                  33143  0 
synoacl_vfs            16969  1 
8021q                  17933  0 
uas                    13557  0 
usb_storage            52935  1 uas
leds_lp3943             4918  0 
aesni_intel           175290  1 
glue_helper             4085  1 aesni_intel
lrw                     3744  1 aesni_intel
gf128mul                5752  1 lrw
ablk_helper             2076  1 aesni_intel
syno_hddmon             2177  0 
geminilake_synobios    83051  0 
hid_generic             1385  0 
usbhid                 26542  0 
hid                    91650  2 hid_generic,usbhid
usblp                  11290  0 
openvswitch            91173  5 
gre                     1651  0 
nf_defrag_ipv6          6487  3 openvswitch,xt_TPROXY,nf_conntrack_ipv6
nf_conntrack           62242  10 ip_vs,openvswitch,nf_nat,xt_state,nf_nat_ipv4,xt_conntrack,nf_nat_masquerade_ipv4,xt_connmark,nf_conntrack_ipv4,nf_conntrack_ipv6
i915                 1293580  1 
drm_kms_helper        121062  1 i915
syscopyarea             3198  1 drm_kms_helper
sysfillrect             3668  1 drm_kms_helper
sysimgblt               2367  1 drm_kms_helper
fb_sys_fops             1442  1 drm_kms_helper
cfbfillrect             3860  1 drm_kms_helper
cfbcopyarea             3390  1 drm_kms_helper
cfbimgblt               2367  1 drm_kms_helper
drm                   310678  4 i915,drm_kms_helper
drm_panel_orientation_quirks     3729  1 drm
iosf_mbi                4298  1 i915
fb                     34821  2 i915,drm_kms_helper
fbdev                   1094  1 fb
video                  27104  1 i915
backlight               6324  2 i915,video
button                  5161  1 i915
i2c_algo_bit            5812  1 i915
uhci_hcd               22005  0 
ehci_pci                4127  0 
ehci_hcd               43205  1 ehci_pci
r8168                 540240  0 
dm_crypt               18450  0 
sg                     26471  0 
dm_snapshot            29850  0 
dm_bufio               14399  1 dm_snapshot
crc_itu_t               1595  1 udf
crc_ccitt               1595  0 
psnap                   2004  0 
p8022                   1307  0 
llc                     3569  4 stp,p8022,psnap,bridge
hfsplus                92606  0 
md4                     3889  0 
hmac                    3089  0 
sit                    15976  0 
tunnel4                 2389  1 sit
ipv6                  318022  599 sit,ip_vs,nf_defrag_ipv6,xt_TPROXY,nf_conntrack_ipv6
flashcache_syno       270416  0 
flashcache             81203  0 
syno_flashcache_control     1231  2 flashcache_syno,flashcache
dm_mod                 90426  10 flashcache_syno,dm_bufio,dm_crypt,flashcache,dm_snapshot
arc4                    2168  0 
crc32c_intel           13333  0 
cryptd                  8677  2 aesni_intel,ablk_helper
ecb                     2241  0 
aes_x86_64              7567  1 aesni_intel
authenc                 4209  0 
des_generic            16285  0 
ansi_cprng              4020  0 
cts                     4520  0 
md5                     2705  0 
cbc                     2776  0 
cpufreq_powersave       1190  0 
cpufreq_performance     1194  4 
acpi_cpufreq            6651  0 
processor              26463  5 acpi_cpufreq
cpufreq_stats           2895  0 
vxlan                  33429  0 
ip6_udp_tunnel          1967  1 vxlan
udp_tunnel              2419  1 vxlan
ip_tunnel              12142  1 sit
zram                   18699  4 
loop                   19321  2 
btrfs                1285275  1 
raid6_pq               97268  1 btrfs
xor                    10808  1 btrfs
zstd_compress         154833  1 btrfs
zstd_decompress        60974  1 btrfs
ecryptfs               85159  1 btrfs
xxhash                  4611  2 zstd_compress,zstd_decompress
sha256_generic         10665  0 
synorbd                81247  0 
synofsbd               31970  0 
etxhci_hcd             84564  0 
xhci_pci                4820  0 
xhci_hcd              111198  1 xhci_pci
usbcore               209065  10 uas,etxhci_hcd,usblp,uhci_hcd,usb_storage,ehci_hcd,ehci_pci,usbhid,xhci_hcd,xhci_pci
usb_common              2881  1 usbcore
