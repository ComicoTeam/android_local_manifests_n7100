LineageOS
===========

Getting started
---------------

```
1. mkdir -p Havoc-OS && cd Havoc-OS

2. Initialize your local repository using the LineageOS trees with a command
  repo init -u https://github.com/Havoc-OS/android_manifest.git -b pie && repo sync -j16
  
3. Clone this repo:
  git clone https://github.com/ComicoTeam/android_local_manifests_n7100 .repo/local_manifests -b Havoc-Pie

4. Sync LineageOS trees:
  repo sync --no-tags --no-clone-bundle --force-sync -c -j8

5. Generate the keys used for ROM signing:

From the root of your Android tree, run these commands, altering the subject line to reflect your information:

subject='/C=US/ST=California/L=Mountain View/O=Android/OU=Android/CN=Android/emailAddress=android@android.com'
mkdir .android-certs
for x in releasekey platform shared media testkey; do \
    ./development/tools/make_key .android-certs/$x "$subject"; \
done

6. To build:
  . build/envsetup.sh
  lunch lineage_n7100-userdebug
  make -j8 bacon
```
