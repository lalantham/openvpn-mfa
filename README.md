## Usage
**Install OpenVPN**

Install OpenVPN Using `openvpn-install.sh` script

Install Following Packages
```
sudo apt install ca-certificates libpam-google-authenticator qrencode
```

**PAM Path Config**
```
find / -name pam_google_authenticator.so 2>/dev/null
```
* Edit and update PAM template `pam_google_authenticator.so` path

* Create PAM file
```
sudo cp openvpn.pam.template /etc/pam.d/openvpn
```
**Create User**

Create users using manage.sh script
```
sudo ./manage.sh create
```
Generate ZIP file Contains Passwords, Barcode
```
sudo ./create-zip.sh
```
**Credit**

[openvpn_2fa](https://github.com/perfecto25/openvpn_2fa)

[openvpn-install](https://github.com/angristan/openvpn-install)

[OpenVPN-2FA-GoogleAuth](https://github.com/zaheerahmad33/OpenVPN-2FA-GoogleAuth)
