## Scripts
**openvpn-install.sh**

The `openvpn-install.sh` script is used to install or remove OpenVPN on the server. It provides an easy way to set up OpenVPN on your server or remove it if necessary.

**manage.sh**

The `manage.sh` script is a helper script that allows you to manage OpenVPN users. It provides options to create, revoke, or check the status of users.

**create-zip.sh**

The `create-zip.sh` script creates a ZIP file containing the client credentials and information, including the user's password, private key password, and a QR code for 2FA.

## Template File

The `openvpn.pam.template` file is a template for configuring PAM (Pluggable Authentication Module) for OpenVPN. It can be customized according to your OpenVPN setup requirements.

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
