
apache/apisix:2.15.2-debian (debian 11.6)
=========================================
Total: 105 (UNKNOWN: 0, LOW: 76, MEDIUM: 9, HIGH: 19, CRITICAL: 1)

┌──────────────────┬──────────────────┬──────────┬───────────────────────┬──────────────────┬──────────────────────────────────────────────────────────────┐
│     Library      │  Vulnerability   │ Severity │   Installed Version   │  Fixed Version   │                            Title                             │
├──────────────────┼──────────────────┼──────────┼───────────────────────┼──────────────────┼──────────────────────────────────────────────────────────────┤
│ apt              │ CVE-2011-3374    │ LOW      │ 2.2.4                 │                  │ It was found that apt-key in apt, all versions, do not       │
│                  │                  │          │                       │                  │ correctly...                                                 │
│                  │                  │          │                       │                  │ https://avd.aquasec.com/nvd/cve-2011-3374                    │
├──────────────────┼──────────────────┼──────────┼───────────────────────┼──────────────────┼──────────────────────────────────────────────────────────────┤
│ bash             │ CVE-2022-3715    │ HIGH     │ 5.1-2+deb11u1         │                  │ bash: a heap-buffer-overflow in valid_parameter_transform    │
│                  │                  │          │                       │                  │ https://avd.aquasec.com/nvd/cve-2022-3715                    │
├──────────────────┼──────────────────┼──────────┼───────────────────────┼──────────────────┼──────────────────────────────────────────────────────────────┤
│ bsdutils         │ CVE-2022-0563    │ LOW      │ 2.36.1-8+deb11u1      │                  │ util-linux: partial disclosure of arbitrary files in chfn    │
│                  │                  │          │                       │                  │ and chsh when compiled...                                    │
│                  │                  │          │                       │                  │ https://avd.aquasec.com/nvd/cve-2022-0563                    │
├──────────────────┼──────────────────┤          ├───────────────────────┼──────────────────┼──────────────────────────────────────────────────────────────┤
│ coreutils        │ CVE-2016-2781    │          │ 8.32-4                │                  │ coreutils: Non-privileged session can escape to the parent   │
│                  │                  │          │                       │                  │ session in chroot                                            │
│                  │                  │          │                       │                  │ https://avd.aquasec.com/nvd/cve-2016-2781                    │
│                  ├──────────────────┤          │                       ├──────────────────┼──────────────────────────────────────────────────────────────┤
│                  │ CVE-2017-18018   │          │                       │                  │ coreutils: race condition vulnerability in chown and chgrp   │
│                  │                  │          │                       │                  │ https://avd.aquasec.com/nvd/cve-2017-18018                   │
├──────────────────┼──────────────────┼──────────┼───────────────────────┼──────────────────┼──────────────────────────────────────────────────────────────┤
│ curl             │ CVE-2022-42916   │ HIGH     │ 7.74.0-1.3+deb11u5    │                  │ curl: HSTS bypass via IDN                                    │
│                  │                  │          │                       │                  │ https://avd.aquasec.com/nvd/cve-2022-42916                   │
│                  ├──────────────────┤          │                       ├──────────────────┼──────────────────────────────────────────────────────────────┤
│                  │ CVE-2022-43551   │          │                       │                  │ curl: HSTS bypass via IDN                                    │
│                  │                  │          │                       │                  │ https://avd.aquasec.com/nvd/cve-2022-43551                   │
│                  ├──────────────────┼──────────┤                       ├──────────────────┼──────────────────────────────────────────────────────────────┤
│                  │ CVE-2023-23916   │ MEDIUM   │                       │                  │ [curl: HTTP multi-header compression denial of service]      │
│                  │                  │          │                       │                  │ https://avd.aquasec.com/nvd/cve-2023-23916                   │
│                  ├──────────────────┼──────────┤                       ├──────────────────┼──────────────────────────────────────────────────────────────┤
│                  │ CVE-2021-22922   │ LOW      │                       │                  │ curl: Content not matching hash in Metalink is not being     │
│                  │                  │          │                       │                  │ discarded                                                    │
│                  │                  │          │                       │                  │ https://avd.aquasec.com/nvd/cve-2021-22922                   │
│                  ├──────────────────┤          │                       ├──────────────────┼──────────────────────────────────────────────────────────────┤
│                  │ CVE-2021-22923   │          │                       │                  │ curl: Metalink download sends credentials                    │
│                  │                  │          │                       │                  │ https://avd.aquasec.com/nvd/cve-2021-22923                   │
│                  ├──────────────────┤          │                       ├──────────────────┼──────────────────────────────────────────────────────────────┤
│                  │ CVE-2023-23914   │          │                       │                  │ [curl: HSTS ignored on multiple requests]                    │
│                  │                  │          │                       │                  │ https://avd.aquasec.com/nvd/cve-2023-23914                   │
│                  ├──────────────────┤          │                       ├──────────────────┼──────────────────────────────────────────────────────────────┤
│                  │ CVE-2023-23915   │          │                       │                  │ [curl: HSTS amnesia with --parallel]                         │
│                  │                  │          │                       │                  │ https://avd.aquasec.com/nvd/cve-2023-23915                   │
├──────────────────┼──────────────────┼──────────┼───────────────────────┼──────────────────┼──────────────────────────────────────────────────────────────┤
│ e2fsprogs        │ CVE-2022-1304    │ HIGH     │ 1.46.2-2              │                  │ e2fsprogs: out-of-bounds read/write via crafted filesystem   │
│                  │                  │          │                       │                  │ https://avd.aquasec.com/nvd/cve-2022-1304                    │
├──────────────────┼──────────────────┼──────────┼───────────────────────┼──────────────────┼──────────────────────────────────────────────────────────────┤
│ libapt-pkg6.0    │ CVE-2011-3374    │ LOW      │ 2.2.4                 │                  │ It was found that apt-key in apt, all versions, do not       │
│                  │                  │          │                       │                  │ correctly...                                                 │
│                  │                  │          │                       │                  │ https://avd.aquasec.com/nvd/cve-2011-3374                    │
├──────────────────┼──────────────────┤          ├───────────────────────┼──────────────────┼──────────────────────────────────────────────────────────────┤
│ libblkid1        │ CVE-2022-0563    │          │ 2.36.1-8+deb11u1      │                  │ util-linux: partial disclosure of arbitrary files in chfn    │
│                  │                  │          │                       │                  │ and chsh when compiled...                                    │
│                  │                  │          │                       │                  │ https://avd.aquasec.com/nvd/cve-2022-0563                    │
├──────────────────┼──────────────────┤          ├───────────────────────┼──────────────────┼──────────────────────────────────────────────────────────────┤
│ libc-bin         │ CVE-2010-4756    │          │ 2.31-13+deb11u5       │                  │ glibc: glob implementation can cause excessive CPU and       │
│                  │                  │          │                       │                  │ memory consumption due to...                                 │
│                  │                  │          │                       │                  │ https://avd.aquasec.com/nvd/cve-2010-4756                    │
│                  ├──────────────────┤          │                       ├──────────────────┼──────────────────────────────────────────────────────────────┤
│                  │ CVE-2018-20796   │          │                       │                  │ glibc: uncontrolled recursion in function                    │
│                  │                  │          │                       │                  │ check_dst_limits_calc_pos_1 in posix/regexec.c               │
│                  │                  │          │                       │                  │ https://avd.aquasec.com/nvd/cve-2018-20796                   │
│                  ├──────────────────┤          │                       ├──────────────────┼──────────────────────────────────────────────────────────────┤
│                  │ CVE-2019-1010022 │          │                       │                  │ glibc: stack guard protection bypass                         │
│                  │                  │          │                       │                  │ https://avd.aquasec.com/nvd/cve-2019-1010022                 │
│                  ├──────────────────┤          │                       ├──────────────────┼──────────────────────────────────────────────────────────────┤
│                  │ CVE-2019-1010023 │          │                       │                  │ glibc: running ldd on malicious ELF leads to code execution  │
│                  │                  │          │                       │                  │ because of...                                                │
│                  │                  │          │                       │                  │ https://avd.aquasec.com/nvd/cve-2019-1010023                 │
│                  ├──────────────────┤          │                       ├──────────────────┼──────────────────────────────────────────────────────────────┤
│                  │ CVE-2019-1010024 │          │                       │                  │ glibc: ASLR bypass using cache of thread stack and heap      │
│                  │                  │          │                       │                  │ https://avd.aquasec.com/nvd/cve-2019-1010024                 │
│                  ├──────────────────┤          │                       ├──────────────────┼──────────────────────────────────────────────────────────────┤
│                  │ CVE-2019-1010025 │          │                       │                  │ glibc: information disclosure of heap addresses of           │
│                  │                  │          │                       │                  │ pthread_created thread                                       │
│                  │                  │          │                       │                  │ https://avd.aquasec.com/nvd/cve-2019-1010025                 │
│                  ├──────────────────┤          │                       ├──────────────────┼──────────────────────────────────────────────────────────────┤
│                  │ CVE-2019-9192    │          │                       │                  │ glibc: uncontrolled recursion in function                    │
│                  │                  │          │                       │                  │ check_dst_limits_calc_pos_1 in posix/regexec.c               │
│                  │                  │          │                       │                  │ https://avd.aquasec.com/nvd/cve-2019-9192                    │
├──────────────────┼──────────────────┤          │                       ├──────────────────┼──────────────────────────────────────────────────────────────┤
│ libc6            │ CVE-2010-4756    │          │                       │                  │ glibc: glob implementation can cause excessive CPU and       │
│                  │                  │          │                       │                  │ memory consumption due to...                                 │
│                  │                  │          │                       │                  │ https://avd.aquasec.com/nvd/cve-2010-4756                    │
│                  ├──────────────────┤          │                       ├──────────────────┼──────────────────────────────────────────────────────────────┤
│                  │ CVE-2018-20796   │          │                       │                  │ glibc: uncontrolled recursion in function                    │
│                  │                  │          │                       │                  │ check_dst_limits_calc_pos_1 in posix/regexec.c               │
│                  │                  │          │                       │                  │ https://avd.aquasec.com/nvd/cve-2018-20796                   │
│                  ├──────────────────┤          │                       ├──────────────────┼──────────────────────────────────────────────────────────────┤
│                  │ CVE-2019-1010022 │          │                       │                  │ glibc: stack guard protection bypass                         │
│                  │                  │          │                       │                  │ https://avd.aquasec.com/nvd/cve-2019-1010022                 │
│                  ├──────────────────┤          │                       ├──────────────────┼──────────────────────────────────────────────────────────────┤
│                  │ CVE-2019-1010023 │          │                       │                  │ glibc: running ldd on malicious ELF leads to code execution  │
│                  │                  │          │                       │                  │ because of...                                                │
│                  │                  │          │                       │                  │ https://avd.aquasec.com/nvd/cve-2019-1010023                 │
│                  ├──────────────────┤          │                       ├──────────────────┼──────────────────────────────────────────────────────────────┤
│                  │ CVE-2019-1010024 │          │                       │                  │ glibc: ASLR bypass using cache of thread stack and heap      │
│                  │                  │          │                       │                  │ https://avd.aquasec.com/nvd/cve-2019-1010024                 │
│                  ├──────────────────┤          │                       ├──────────────────┼──────────────────────────────────────────────────────────────┤
│                  │ CVE-2019-1010025 │          │                       │                  │ glibc: information disclosure of heap addresses of           │
│                  │                  │          │                       │                  │ pthread_created thread                                       │
│                  │                  │          │                       │                  │ https://avd.aquasec.com/nvd/cve-2019-1010025                 │
│                  ├──────────────────┤          │                       ├──────────────────┼──────────────────────────────────────────────────────────────┤
│                  │ CVE-2019-9192    │          │                       │                  │ glibc: uncontrolled recursion in function                    │
│                  │                  │          │                       │                  │ check_dst_limits_calc_pos_1 in posix/regexec.c               │
│                  │                  │          │                       │                  │ https://avd.aquasec.com/nvd/cve-2019-9192                    │
├──────────────────┼──────────────────┼──────────┼───────────────────────┼──────────────────┼──────────────────────────────────────────────────────────────┤
│ libcom-err2      │ CVE-2022-1304    │ HIGH     │ 1.46.2-2              │                  │ e2fsprogs: out-of-bounds read/write via crafted filesystem   │
│                  │                  │          │                       │                  │ https://avd.aquasec.com/nvd/cve-2022-1304                    │
├──────────────────┼──────────────────┤          ├───────────────────────┼──────────────────┼──────────────────────────────────────────────────────────────┤
│ libcurl4         │ CVE-2022-42916   │          │ 7.74.0-1.3+deb11u5    │                  │ curl: HSTS bypass via IDN                                    │
│                  │                  │          │                       │                  │ https://avd.aquasec.com/nvd/cve-2022-42916                   │
│                  ├──────────────────┤          │                       ├──────────────────┼──────────────────────────────────────────────────────────────┤
│                  │ CVE-2022-43551   │          │                       │                  │ curl: HSTS bypass via IDN                                    │
│                  │                  │          │                       │                  │ https://avd.aquasec.com/nvd/cve-2022-43551                   │
│                  ├──────────────────┼──────────┤                       ├──────────────────┼──────────────────────────────────────────────────────────────┤
│                  │ CVE-2023-23916   │ MEDIUM   │                       │                  │ [curl: HTTP multi-header compression denial of service]      │
│                  │                  │          │                       │                  │ https://avd.aquasec.com/nvd/cve-2023-23916                   │
│                  ├──────────────────┼──────────┤                       ├──────────────────┼──────────────────────────────────────────────────────────────┤
│                  │ CVE-2021-22922   │ LOW      │                       │                  │ curl: Content not matching hash in Metalink is not being     │
│                  │                  │          │                       │                  │ discarded                                                    │
│                  │                  │          │                       │                  │ https://avd.aquasec.com/nvd/cve-2021-22922                   │
│                  ├──────────────────┤          │                       ├──────────────────┼──────────────────────────────────────────────────────────────┤
│                  │ CVE-2021-22923   │          │                       │                  │ curl: Metalink download sends credentials                    │
│                  │                  │          │                       │                  │ https://avd.aquasec.com/nvd/cve-2021-22923                   │
│                  ├──────────────────┤          │                       ├──────────────────┼──────────────────────────────────────────────────────────────┤
│                  │ CVE-2023-23914   │          │                       │                  │ [curl: HSTS ignored on multiple requests]                    │
│                  │                  │          │                       │                  │ https://avd.aquasec.com/nvd/cve-2023-23914                   │
│                  ├──────────────────┤          │                       ├──────────────────┼──────────────────────────────────────────────────────────────┤
│                  │ CVE-2023-23915   │          │                       │                  │ [curl: HSTS amnesia with --parallel]                         │
│                  │                  │          │                       │                  │ https://avd.aquasec.com/nvd/cve-2023-23915                   │
├──────────────────┼──────────────────┼──────────┼───────────────────────┼──────────────────┼──────────────────────────────────────────────────────────────┤
│ libdb5.3         │ CVE-2019-8457    │ CRITICAL │ 5.3.28+dfsg1-0.8      │                  │ sqlite: heap out-of-bound read in function rtreenode()       │
│                  │                  │          │                       │                  │ https://avd.aquasec.com/nvd/cve-2019-8457                    │
├──────────────────┼──────────────────┼──────────┼───────────────────────┼──────────────────┼──────────────────────────────────────────────────────────────┤
│ libext2fs2       │ CVE-2022-1304    │ HIGH     │ 1.46.2-2              │                  │ e2fsprogs: out-of-bounds read/write via crafted filesystem   │
│                  │                  │          │                       │                  │ https://avd.aquasec.com/nvd/cve-2022-1304                    │
├──────────────────┼──────────────────┤          ├───────────────────────┼──────────────────┼──────────────────────────────────────────────────────────────┤
│ libgcrypt20      │ CVE-2021-33560   │          │ 1.8.7-6               │                  │ libgcrypt: mishandles ElGamal encryption because it lacks    │
│                  │                  │          │                       │                  │ exponent blinding to address a...                            │
│                  │                  │          │                       │                  │ https://avd.aquasec.com/nvd/cve-2021-33560                   │
│                  ├──────────────────┼──────────┤                       ├──────────────────┼──────────────────────────────────────────────────────────────┤
│                  │ CVE-2018-6829    │ LOW      │                       │                  │ libgcrypt: ElGamal implementation doesn't have semantic      │
│                  │                  │          │                       │                  │ security due to incorrectly encoded plaintexts...            │
│                  │                  │          │                       │                  │ https://avd.aquasec.com/nvd/cve-2018-6829                    │
├──────────────────┼──────────────────┼──────────┼───────────────────────┼──────────────────┼──────────────────────────────────────────────────────────────┤
│ libgnutls30      │ CVE-2023-0361    │ MEDIUM   │ 3.7.1-5+deb11u2       │ 3.7.1-5+deb11u3  │ A timing side-channel in the handling of RSA                 │
│                  │                  │          │                       │                  │ ClientKeyExchange message ...                                │
│                  │                  │          │                       │                  │ https://avd.aquasec.com/nvd/cve-2023-0361                    │
│                  ├──────────────────┼──────────┤                       ├──────────────────┼──────────────────────────────────────────────────────────────┤
│                  │ CVE-2011-3389    │ LOW      │                       │                  │ HTTPS: block-wise chosen-plaintext attack against SSL/TLS    │
│                  │                  │          │                       │                  │ (BEAST)                                                      │
│                  │                  │          │                       │                  │ https://avd.aquasec.com/nvd/cve-2011-3389                    │
├──────────────────┼──────────────────┤          ├───────────────────────┼──────────────────┼──────────────────────────────────────────────────────────────┤
│ libgssapi-krb5-2 │ CVE-2018-5709    │          │ 1.18.3-6+deb11u3      │                  │ krb5: integer overflow in dbentry->n_key_data in             │
│                  │                  │          │                       │                  │ kadmin/dbutil/dump.c                                         │
│                  │                  │          │                       │                  │ https://avd.aquasec.com/nvd/cve-2018-5709                    │
├──────────────────┤                  │          │                       ├──────────────────┤                                                              │
│ libk5crypto3     │                  │          │                       │                  │                                                              │
│                  │                  │          │                       │                  │                                                              │
│                  │                  │          │                       │                  │                                                              │
├──────────────────┤                  │          │                       ├──────────────────┤                                                              │
│ libkrb5-3        │                  │          │                       │                  │                                                              │
│                  │                  │          │                       │                  │                                                              │
│                  │                  │          │                       │                  │                                                              │
├──────────────────┤                  │          │                       ├──────────────────┤                                                              │
│ libkrb5support0  │                  │          │                       │                  │                                                              │
│                  │                  │          │                       │                  │                                                              │
│                  │                  │          │                       │                  │                                                              │
├──────────────────┼──────────────────┤          ├───────────────────────┼──────────────────┼──────────────────────────────────────────────────────────────┤
│ libldap-2.4-2    │ CVE-2015-3276    │          │ 2.4.57+dfsg-3+deb11u1 │                  │ openldap: incorrect multi-keyword mode cipherstring parsing  │
│                  │                  │          │                       │                  │ https://avd.aquasec.com/nvd/cve-2015-3276                    │
│                  ├──────────────────┤          │                       ├──────────────────┼──────────────────────────────────────────────────────────────┤
│                  │ CVE-2017-14159   │          │                       │                  │ openldap: Privilege escalation via PID file manipulation     │
│                  │                  │          │                       │                  │ https://avd.aquasec.com/nvd/cve-2017-14159                   │
│                  ├──────────────────┤          │                       ├──────────────────┼──────────────────────────────────────────────────────────────┤
│                  │ CVE-2017-17740   │          │                       │                  │ openldap: contrib/slapd-modules/nops/nops.c attempts to free │
│                  │                  │          │                       │                  │ stack buffer allowing remote attackers to cause...           │
│                  │                  │          │                       │                  │ https://avd.aquasec.com/nvd/cve-2017-17740                   │
│                  ├──────────────────┤          │                       ├──────────────────┼──────────────────────────────────────────────────────────────┤
│                  │ CVE-2020-15719   │          │                       │                  │ openldap: Certificate validation incorrectly matches name    │
│                  │                  │          │                       │                  │ against CN-ID                                                │
│                  │                  │          │                       │                  │ https://avd.aquasec.com/nvd/cve-2020-15719                   │
├──────────────────┼──────────────────┤          │                       ├──────────────────┼──────────────────────────────────────────────────────────────┤
│ libldap2-dev     │ CVE-2015-3276    │          │                       │                  │ openldap: incorrect multi-keyword mode cipherstring parsing  │
│                  │                  │          │                       │                  │ https://avd.aquasec.com/nvd/cve-2015-3276                    │
│                  ├──────────────────┤          │                       ├──────────────────┼──────────────────────────────────────────────────────────────┤
│                  │ CVE-2017-14159   │          │                       │                  │ openldap: Privilege escalation via PID file manipulation     │
│                  │                  │          │                       │                  │ https://avd.aquasec.com/nvd/cve-2017-14159                   │
│                  ├──────────────────┤          │                       ├──────────────────┼──────────────────────────────────────────────────────────────┤
│                  │ CVE-2017-17740   │          │                       │                  │ openldap: contrib/slapd-modules/nops/nops.c attempts to free │
│                  │                  │          │                       │                  │ stack buffer allowing remote attackers to cause...           │
│                  │                  │          │                       │                  │ https://avd.aquasec.com/nvd/cve-2017-17740                   │
│                  ├──────────────────┤          │                       ├──────────────────┼──────────────────────────────────────────────────────────────┤
│                  │ CVE-2020-15719   │          │                       │                  │ openldap: Certificate validation incorrectly matches name    │
│                  │                  │          │                       │                  │ against CN-ID                                                │
│                  │                  │          │                       │                  │ https://avd.aquasec.com/nvd/cve-2020-15719                   │
├──────────────────┼──────────────────┤          ├───────────────────────┼──────────────────┼──────────────────────────────────────────────────────────────┤
│ libmount1        │ CVE-2022-0563    │          │ 2.36.1-8+deb11u1      │                  │ util-linux: partial disclosure of arbitrary files in chfn    │
│                  │                  │          │                       │                  │ and chsh when compiled...                                    │
│                  │                  │          │                       │                  │ https://avd.aquasec.com/nvd/cve-2022-0563                    │
├──────────────────┼──────────────────┼──────────┼───────────────────────┼──────────────────┼──────────────────────────────────────────────────────────────┤
│ libncursesw6     │ CVE-2022-29458   │ HIGH     │ 6.2+20201114-2        │                  │ ncurses: segfaulting OOB read                                │
│                  │                  │          │                       │                  │ https://avd.aquasec.com/nvd/cve-2022-29458                   │
├──────────────────┼──────────────────┼──────────┼───────────────────────┼──────────────────┼──────────────────────────────────────────────────────────────┤
│ libpcre3         │ CVE-2017-11164   │ LOW      │ 2:8.39-13             │                  │ pcre: OP_KETRMAX feature in the match function in            │
│                  │                  │          │                       │                  │ pcre_exec.c                                                  │
│                  │                  │          │                       │                  │ https://avd.aquasec.com/nvd/cve-2017-11164                   │
│                  ├──────────────────┤          │                       ├──────────────────┼──────────────────────────────────────────────────────────────┤
│                  │ CVE-2017-16231   │          │                       │                  │ pcre: self-recursive call in match() in pcre_exec.c leads to │
│                  │                  │          │                       │                  │ denial of service...                                         │
│                  │                  │          │                       │                  │ https://avd.aquasec.com/nvd/cve-2017-16231                   │
│                  ├──────────────────┤          │                       ├──────────────────┼──────────────────────────────────────────────────────────────┤
│                  │ CVE-2017-7245    │          │                       │                  │ pcre: stack-based buffer overflow write in                   │
│                  │                  │          │                       │                  │ pcre32_copy_substring                                        │
│                  │                  │          │                       │                  │ https://avd.aquasec.com/nvd/cve-2017-7245                    │
│                  ├──────────────────┤          │                       ├──────────────────┼──────────────────────────────────────────────────────────────┤
│                  │ CVE-2017-7246    │          │                       │                  │ pcre: stack-based buffer overflow write in                   │
│                  │                  │          │                       │                  │ pcre32_copy_substring                                        │
│                  │                  │          │                       │                  │ https://avd.aquasec.com/nvd/cve-2017-7246                    │
│                  ├──────────────────┤          │                       ├──────────────────┼──────────────────────────────────────────────────────────────┤
│                  │ CVE-2019-20838   │          │                       │                  │ pcre: Buffer over-read in JIT when UTF is disabled and \X    │
│                  │                  │          │                       │                  │ or...                                                        │
│                  │                  │          │                       │                  │ https://avd.aquasec.com/nvd/cve-2019-20838                   │
├──────────────────┼──────────────────┤          ├───────────────────────┼──────────────────┼──────────────────────────────────────────────────────────────┤
│ libsepol1        │ CVE-2021-36084   │          │ 3.1-1                 │                  │ libsepol: use-after-free in __cil_verify_classperms()        │
│                  │                  │          │                       │                  │ https://avd.aquasec.com/nvd/cve-2021-36084                   │
│                  ├──────────────────┤          │                       ├──────────────────┼──────────────────────────────────────────────────────────────┤
│                  │ CVE-2021-36085   │          │                       │                  │ libsepol: use-after-free in __cil_verify_classperms()        │
│                  │                  │          │                       │                  │ https://avd.aquasec.com/nvd/cve-2021-36085                   │
│                  ├──────────────────┤          │                       ├──────────────────┼──────────────────────────────────────────────────────────────┤
│                  │ CVE-2021-36086   │          │                       │                  │ libsepol: use-after-free in cil_reset_classpermission()      │
│                  │                  │          │                       │                  │ https://avd.aquasec.com/nvd/cve-2021-36086                   │
│                  ├──────────────────┤          │                       ├──────────────────┼──────────────────────────────────────────────────────────────┤
│                  │ CVE-2021-36087   │          │                       │                  │ libsepol: heap-based buffer overflow in ebitmap_match_any()  │
│                  │                  │          │                       │                  │ https://avd.aquasec.com/nvd/cve-2021-36087                   │
├──────────────────┼──────────────────┤          ├───────────────────────┼──────────────────┼──────────────────────────────────────────────────────────────┤
│ libsmartcols1    │ CVE-2022-0563    │          │ 2.36.1-8+deb11u1      │                  │ util-linux: partial disclosure of arbitrary files in chfn    │
│                  │                  │          │                       │                  │ and chsh when compiled...                                    │
│                  │                  │          │                       │                  │ https://avd.aquasec.com/nvd/cve-2022-0563                    │
├──────────────────┼──────────────────┤          ├───────────────────────┼──────────────────┼──────────────────────────────────────────────────────────────┤
│ libsqlite3-0     │ CVE-2021-36690   │          │ 3.34.1-3              │                  │ ** DISPUTED ** A segmentation fault can occur in the         │
│                  │                  │          │                       │                  │ sqlite3.exe comma...                                         │
│                  │                  │          │                       │                  │ https://avd.aquasec.com/nvd/cve-2021-36690                   │
│                  ├──────────────────┤          │                       ├──────────────────┼──────────────────────────────────────────────────────────────┤
│                  │ CVE-2021-45346   │          │                       │                  │ sqlite: crafted SQL query allows a malicious user to obtain  │
│                  │                  │          │                       │                  │ sensitive information...                                     │
│                  │                  │          │                       │                  │ https://avd.aquasec.com/nvd/cve-2021-45346                   │
│                  ├──────────────────┤          │                       ├──────────────────┼──────────────────────────────────────────────────────────────┤
│                  │ CVE-2022-35737   │          │                       │                  │ sqlite: an array-bounds overflow if billions of bytes are    │
│                  │                  │          │                       │                  │ used in a...                                                 │
│                  │                  │          │                       │                  │ https://avd.aquasec.com/nvd/cve-2022-35737                   │
├──────────────────┼──────────────────┼──────────┼───────────────────────┼──────────────────┼──────────────────────────────────────────────────────────────┤
│ libss2           │ CVE-2022-1304    │ HIGH     │ 1.46.2-2              │                  │ e2fsprogs: out-of-bounds read/write via crafted filesystem   │
│                  │                  │          │                       │                  │ https://avd.aquasec.com/nvd/cve-2022-1304                    │
├──────────────────┼──────────────────┤          ├───────────────────────┼──────────────────┼──────────────────────────────────────────────────────────────┤
│ libssl1.1        │ CVE-2022-4450    │          │ 1.1.1n-0+deb11u3      │ 1.1.1n-0+deb11u4 │ The function PEM_read_bio_ex() reads a PEM file from a BIO   │
│                  │                  │          │                       │                  │ and parses...                                                │
│                  │                  │          │                       │                  │ https://avd.aquasec.com/nvd/cve-2022-4450                    │
│                  ├──────────────────┤          │                       │                  ├──────────────────────────────────────────────────────────────┤
│                  │ CVE-2023-0215    │          │                       │                  │ The public API function BIO_new_NDEF is a helper function    │
│                  │                  │          │                       │                  │ used for str...                                              │
│                  │                  │          │                       │                  │ https://avd.aquasec.com/nvd/cve-2023-0215                    │
│                  ├──────────────────┤          │                       │                  ├──────────────────────────────────────────────────────────────┤
│                  │ CVE-2023-0286    │          │                       │                  │ There is a type confusion vulnerability relating to X.400    │
│                  │                  │          │                       │                  │ address proc ......                                          │
│                  │                  │          │                       │                  │ https://avd.aquasec.com/nvd/cve-2023-0286                    │
│                  ├──────────────────┼──────────┤                       │                  ├──────────────────────────────────────────────────────────────┤
│                  │ CVE-2022-2097    │ MEDIUM   │                       │                  │ openssl: AES OCB fails to encrypt some bytes                 │
│                  │                  │          │                       │                  │ https://avd.aquasec.com/nvd/cve-2022-2097                    │
│                  ├──────────────────┤          │                       │                  ├──────────────────────────────────────────────────────────────┤
│                  │ CVE-2022-4304    │          │                       │                  │ A timing based side channel exists in the OpenSSL RSA        │
│                  │                  │          │                       │                  │ Decryption imple...                                          │
│                  │                  │          │                       │                  │ https://avd.aquasec.com/nvd/cve-2022-4304                    │
│                  ├──────────────────┼──────────┤                       ├──────────────────┼──────────────────────────────────────────────────────────────┤
│                  │ CVE-2007-6755    │ LOW      │                       │                  │ Dual_EC_DRBG: weak pseudo random number generator            │
│                  │                  │          │                       │                  │ https://avd.aquasec.com/nvd/cve-2007-6755                    │
│                  ├──────────────────┤          │                       ├──────────────────┼──────────────────────────────────────────────────────────────┤
│                  │ CVE-2010-0928    │          │                       │                  │ openssl: RSA authentication weakness                         │
│                  │                  │          │                       │                  │ https://avd.aquasec.com/nvd/cve-2010-0928                    │
├──────────────────┼──────────────────┼──────────┼───────────────────────┼──────────────────┼──────────────────────────────────────────────────────────────┤
│ libsystemd0      │ CVE-2022-3821    │ MEDIUM   │ 247.3-7+deb11u1       │                  │ systemd: buffer overrun in format_timespan() function        │
│                  │                  │          │                       │                  │ https://avd.aquasec.com/nvd/cve-2022-3821                    │
│                  ├──────────────────┤          │                       ├──────────────────┼──────────────────────────────────────────────────────────────┤
│                  │ CVE-2022-4415    │          │                       │                  │ systemd: local information leak due to systemd-coredump not  │
│                  │                  │          │                       │                  │ respecting fs.suid_dumpable kernel setting...                │
│                  │                  │          │                       │                  │ https://avd.aquasec.com/nvd/cve-2022-4415                    │
│                  ├──────────────────┼──────────┤                       ├──────────────────┼──────────────────────────────────────────────────────────────┤
│                  │ CVE-2013-4392    │ LOW      │                       │                  │ systemd: TOCTOU race condition when updating file            │
│                  │                  │          │                       │                  │ permissions and SELinux security contexts...                 │
│                  │                  │          │                       │                  │ https://avd.aquasec.com/nvd/cve-2013-4392                    │
│                  ├──────────────────┤          │                       ├──────────────────┼──────────────────────────────────────────────────────────────┤
│                  │ CVE-2020-13529   │          │                       │                  │ systemd: DHCP FORCERENEW authentication not implemented can  │
│                  │                  │          │                       │                  │ cause a system running the...                                │
│                  │                  │          │                       │                  │ https://avd.aquasec.com/nvd/cve-2020-13529                   │
├──────────────────┼──────────────────┼──────────┼───────────────────────┼──────────────────┼──────────────────────────────────────────────────────────────┤
│ libtinfo6        │ CVE-2022-29458   │ HIGH     │ 6.2+20201114-2        │                  │ ncurses: segfaulting OOB read                                │
│                  │                  │          │                       │                  │ https://avd.aquasec.com/nvd/cve-2022-29458                   │
├──────────────────┼──────────────────┼──────────┼───────────────────────┼──────────────────┼──────────────────────────────────────────────────────────────┤
│ libudev1         │ CVE-2022-3821    │ MEDIUM   │ 247.3-7+deb11u1       │                  │ systemd: buffer overrun in format_timespan() function        │
│                  │                  │          │                       │                  │ https://avd.aquasec.com/nvd/cve-2022-3821                    │
│                  ├──────────────────┤          │                       ├──────────────────┼──────────────────────────────────────────────────────────────┤
│                  │ CVE-2022-4415    │          │                       │                  │ systemd: local information leak due to systemd-coredump not  │
│                  │                  │          │                       │                  │ respecting fs.suid_dumpable kernel setting...                │
│                  │                  │          │                       │                  │ https://avd.aquasec.com/nvd/cve-2022-4415                    │
│                  ├──────────────────┼──────────┤                       ├──────────────────┼──────────────────────────────────────────────────────────────┤
│                  │ CVE-2013-4392    │ LOW      │                       │                  │ systemd: TOCTOU race condition when updating file            │
│                  │                  │          │                       │                  │ permissions and SELinux security contexts...                 │
│                  │                  │          │                       │                  │ https://avd.aquasec.com/nvd/cve-2013-4392                    │
│                  ├──────────────────┤          │                       ├──────────────────┼──────────────────────────────────────────────────────────────┤
│                  │ CVE-2020-13529   │          │                       │                  │ systemd: DHCP FORCERENEW authentication not implemented can  │
│                  │                  │          │                       │                  │ cause a system running the...                                │
│                  │                  │          │                       │                  │ https://avd.aquasec.com/nvd/cve-2020-13529                   │
├──────────────────┼──────────────────┤          ├───────────────────────┼──────────────────┼──────────────────────────────────────────────────────────────┤
│ libuuid1         │ CVE-2022-0563    │          │ 2.36.1-8+deb11u1      │                  │ util-linux: partial disclosure of arbitrary files in chfn    │
│                  │                  │          │                       │                  │ and chsh when compiled...                                    │
│                  │                  │          │                       │                  │ https://avd.aquasec.com/nvd/cve-2022-0563                    │
├──────────────────┼──────────────────┤          ├───────────────────────┼──────────────────┼──────────────────────────────────────────────────────────────┤
│ login            │ CVE-2007-5686    │          │ 1:4.8.1-1             │                  │ initscripts in rPath Linux 1 sets insecure permissions for   │
│                  │                  │          │                       │                  │ the /var/lo ......                                           │
│                  │                  │          │                       │                  │ https://avd.aquasec.com/nvd/cve-2007-5686                    │
│                  ├──────────────────┤          │                       ├──────────────────┼──────────────────────────────────────────────────────────────┤
│                  │ CVE-2013-4235    │          │                       │                  │ shadow-utils: TOCTOU race conditions by copying and removing │
│                  │                  │          │                       │                  │ directory trees                                              │
│                  │                  │          │                       │                  │ https://avd.aquasec.com/nvd/cve-2013-4235                    │
│                  ├──────────────────┤          │                       ├──────────────────┼──────────────────────────────────────────────────────────────┤
│                  │ CVE-2019-19882   │          │                       │                  │ shadow-utils: local users can obtain root access because     │
│                  │                  │          │                       │                  │ setuid programs are misconfigured...                         │
│                  │                  │          │                       │                  │ https://avd.aquasec.com/nvd/cve-2019-19882                   │
├──────────────────┼──────────────────┼──────────┼───────────────────────┼──────────────────┼──────────────────────────────────────────────────────────────┤
│ logsave          │ CVE-2022-1304    │ HIGH     │ 1.46.2-2              │                  │ e2fsprogs: out-of-bounds read/write via crafted filesystem   │
│                  │                  │          │                       │                  │ https://avd.aquasec.com/nvd/cve-2022-1304                    │
├──────────────────┼──────────────────┼──────────┼───────────────────────┼──────────────────┼──────────────────────────────────────────────────────────────┤
│ mount            │ CVE-2022-0563    │ LOW      │ 2.36.1-8+deb11u1      │                  │ util-linux: partial disclosure of arbitrary files in chfn    │
│                  │                  │          │                       │                  │ and chsh when compiled...                                    │
│                  │                  │          │                       │                  │ https://avd.aquasec.com/nvd/cve-2022-0563                    │
├──────────────────┼──────────────────┼──────────┼───────────────────────┼──────────────────┼──────────────────────────────────────────────────────────────┤
│ ncurses-base     │ CVE-2022-29458   │ HIGH     │ 6.2+20201114-2        │                  │ ncurses: segfaulting OOB read                                │
│                  │                  │          │                       │                  │ https://avd.aquasec.com/nvd/cve-2022-29458                   │
├──────────────────┤                  │          │                       ├──────────────────┤                                                              │
│ ncurses-bin      │                  │          │                       │                  │                                                              │
│                  │                  │          │                       │                  │                                                              │
├──────────────────┼──────────────────┼──────────┼───────────────────────┼──────────────────┼──────────────────────────────────────────────────────────────┤
│ openssl          │ CVE-2007-6755    │ LOW      │ 1.1.1n-0+deb11u4      │                  │ Dual_EC_DRBG: weak pseudo random number generator            │
│                  │                  │          │                       │                  │ https://avd.aquasec.com/nvd/cve-2007-6755                    │
│                  ├──────────────────┤          │                       ├──────────────────┼──────────────────────────────────────────────────────────────┤
│                  │ CVE-2010-0928    │          │                       │                  │ openssl: RSA authentication weakness                         │
│                  │                  │          │                       │                  │ https://avd.aquasec.com/nvd/cve-2010-0928                    │
├──────────────────┼──────────────────┤          ├───────────────────────┼──────────────────┼──────────────────────────────────────────────────────────────┤
│ passwd           │ CVE-2007-5686    │          │ 1:4.8.1-1             │                  │ initscripts in rPath Linux 1 sets insecure permissions for   │
│                  │                  │          │                       │                  │ the /var/lo ......                                           │
│                  │                  │          │                       │                  │ https://avd.aquasec.com/nvd/cve-2007-5686                    │
│                  ├──────────────────┤          │                       ├──────────────────┼──────────────────────────────────────────────────────────────┤
│                  │ CVE-2013-4235    │          │                       │                  │ shadow-utils: TOCTOU race conditions by copying and removing │
│                  │                  │          │                       │                  │ directory trees                                              │
│                  │                  │          │                       │                  │ https://avd.aquasec.com/nvd/cve-2013-4235                    │
│                  ├──────────────────┤          │                       ├──────────────────┼──────────────────────────────────────────────────────────────┤
│                  │ CVE-2019-19882   │          │                       │                  │ shadow-utils: local users can obtain root access because     │
│                  │                  │          │                       │                  │ setuid programs are misconfigured...                         │
│                  │                  │          │                       │                  │ https://avd.aquasec.com/nvd/cve-2019-19882                   │
├──────────────────┼──────────────────┼──────────┼───────────────────────┼──────────────────┼──────────────────────────────────────────────────────────────┤
│ perl-base        │ CVE-2020-16156   │ HIGH     │ 5.32.1-4+deb11u2      │                  │ perl-CPAN: Bypass of verification of signatures in CHECKSUMS │
│                  │                  │          │                       │                  │ files                                                        │
│                  │                  │          │                       │                  │ https://avd.aquasec.com/nvd/cve-2020-16156                   │
│                  ├──────────────────┼──────────┤                       ├──────────────────┼──────────────────────────────────────────────────────────────┤
│                  │ CVE-2011-4116    │ LOW      │                       │                  │ perl: File::Temp insecure temporary file handling            │
│                  │                  │          │                       │                  │ https://avd.aquasec.com/nvd/cve-2011-4116                    │
├──────────────────┼──────────────────┤          ├───────────────────────┼──────────────────┼──────────────────────────────────────────────────────────────┤
│ tar              │ CVE-2005-2541    │          │ 1.34+dfsg-1           │                  │ tar: does not properly warn the user when extracting setuid  │
│                  │                  │          │                       │                  │ or setgid...                                                 │
│                  │                  │          │                       │                  │ https://avd.aquasec.com/nvd/cve-2005-2541                    │
│                  ├──────────────────┤          │                       ├──────────────────┼──────────────────────────────────────────────────────────────┤
│                  │ CVE-2022-48303   │          │                       │                  │ tar: heap buffer overflow at from_header() in list.c via     │
│                  │                  │          │                       │                  │ specially crafted checksum...                                │
│                  │                  │          │                       │                  │ https://avd.aquasec.com/nvd/cve-2022-48303                   │
├──────────────────┼──────────────────┤          ├───────────────────────┼──────────────────┼──────────────────────────────────────────────────────────────┤
│ util-linux       │ CVE-2022-0563    │          │ 2.36.1-8+deb11u1      │                  │ util-linux: partial disclosure of arbitrary files in chfn    │
│                  │                  │          │                       │                  │ and chsh when compiled...                                    │
│                  │                  │          │                       │                  │ https://avd.aquasec.com/nvd/cve-2022-0563                    │
└──────────────────┴──────────────────┴──────────┴───────────────────────┴──────────────────┴──────────────────────────────────────────────────────────────┘

/usr/local/apisix/conf/cert/ssl_PLACE_HOLDER.key (secrets)
==========================================================
Total: 1 (UNKNOWN: 0, LOW: 0, MEDIUM: 0, HIGH: 1, CRITICAL: 0)

HIGH: AsymmetricPrivateKey (private-key)
══════════════════════════════════════════════════════════════════════════════════════════════════════════════════════════════════════════════
Asymmetric Private Key
──────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────
 /usr/local/apisix/conf/cert/ssl_PLACE_HOLDER.key:1 (added by 'RUN |1 APISIX_VERSION=2.15.2 /bin/sh -c ')
──────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────
   1 [ -----BEGIN RSA PRIVATE KEY-----**********************************************************************************************************************************************************************************************************************************************************************************************************************************************************************************************************************************************************************************************************************************************************************************************************************************************************************************************************************************************************************************************************************************************************************************************************************************************************************************************************************************************************************************************************************************************************************************************************************************************************************************************************************************************************************************************************************************************************************************************************************************************************************************************************************************************************************************************************************************************************************************************************************************************************************************************************************************************************************************************************************************************************************************************************************************************************************************************************************************************************************************************************************************************************************************************************************************************************************************************-----END RSA PRIVATE KEY-----
   2   
──────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────

