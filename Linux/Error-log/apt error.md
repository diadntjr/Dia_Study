# apt Error
<p></p>

## 1. apt-get install lock error
오류 내용: <br>
E: Could not get lock /var/lib/dpkg/lock’
<br><br>
해결 방안: <br>

```bash
#first
sudo killall apt apt-get

# second
sudo rm /var/lib/apt/lists/lock
sudo rm /var/cache/apt/archives/lock
sudo rm /var/lib/dpkg/lock*

sudo dpkg --configure -a && sudo apt update
```

https://askubuntu.com/questions/521770/error-parsing-file-var-lib-dpkg-updates-0001-near-line-0-newline-in-field-n

```bash
sudo mv /var/lib/dpkg/updates/0001 /var/lib/dpkg/updates/0001.X

# after that
sudo dpkg --configure -a
sudo apt-get install -f
```