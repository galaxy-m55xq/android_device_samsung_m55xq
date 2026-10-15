# Android device tree for samsung SM-M556B (m55xq)

## Make Lineage-24.0 Directory
```
mkdir lineage-24.0; cd lineage-24.0
```
## Init lineage-24.0
```
repo init -u https://github.com/LineageOS/android.git -b lineage-24.0 --git-lfs
```
## Manifest: Latest (lineage-24.0)
```
mkdir -p .repo/local_manifests

cat > .repo/local_manifests/roomservice.xml
<< 'EOF'
<?xml version="1.0" encoding="UTF-8"?>
<manifest>
<!-- Device + Vendor -->
<project name="galaxy-m55xq/android_device_samsung_m55xq" path="device/samsung/m55xq" remote="github" revision="lineage-24.0-kernel-wire-up" />
<project name="galaxy-m55xq/android_vendor_samsung_m55xq" path="vendor/samsung/m55xq" remote="github" revision="M556BXXS5DZF2" />
<project name="LineageOS/android_hardware_samsung" path="hardware/samsung" remote="github" revision="lineage-24.0" />
<!-- ======================== -->
<!-- QCOM CAF - Audio (Taro)  -->
<!-- ======================== -->
<project path="hardware/qcom-caf/sm8450/audio/agm"
       name="LineageOS/android_vendor_qcom_opensource_agm"
       remote="github"
       revision="lineage-24.0-caf-sm8450" />       
<project path="hardware/qcom-caf/sm8450/audio/pal"
       name="LineageOS/android_vendor_qcom_opensource_arpal-lx"
       remote="github"
       revision="lineage-24.0-caf-sm8450" />
<project path="hardware/qcom-caf/sm8450/audio/primary-hal"
       name="LineageOS/android_hardware_qcom_audio-ar"
       remote="github"
       revision="lineage-24.0-caf-sm8450" />
<project path="hardware/qcom-caf/sm8450/audio/graphservices"
       name="LineageOS/android_vendor_qcom_opensource_audioreach-graphservices"
       remote="github"
       revision="lineage-24.0-caf-sm8450" />
<!-- ======================== -->
<!-- QCOM CAF - Display       -->
<!-- ======================== -->
<project path="hardware/qcom-caf/sm8450/display"
       name="LineageOS/android_hardware_qcom_display"
       remote="github"
       revision="lineage-24.0-caf-sm8450" />
<!-- ======================== -->
<!-- QCOM CAF - Data / IPA    -->
<!-- ======================== -->
<project path="hardware/qcom-caf/sm8450/data-ipa-cfg-mgr"
       name="LineageOS/android_vendor_qcom_opensource_data-ipa-cfg-mgr"
       remote="github"
       revision="lineage-24.0-caf-sm8450" />
<!-- ======================== -->
<!-- QCOM Opensource HALs     -->
<!-- ======================== -->
<project path="vendor/qcom/opensource/power"
       name="LineageOS/android_vendor_qcom_opensource_power"
       remote="github"
       revision="lineage-24.0" />
<project path="vendor/qcom/opensource/vibrator"
       name="LineageOS/android_vendor_qcom_opensource_vibrator"
       remote="github"
       revision="lineage-24.0" />
<project path="vendor/qcom/opensource/usb"
       name="LineageOS/android_vendor_qcom_opensource_usb"
       remote="github"
       revision="lineage-24.0" />
<project path="vendor/qcom/opensource/thermal-engine"
       name="LineageOS/android_vendor_qcom_opensource_thermal-engine"
       remote="github"
       revision="lineage-24.0" />
<project path="vendor/qcom/opensource/interfaces"
       name="LineageOS/android_vendor_qcom_opensource_interfaces"
       remote="github"
       revision="lineage-24.0" />
<!-- Sound Trigger (needed for PAL/AGM audio) -->
<project path="vendor/qcom/opensource/audio-hal/st-hal-ar"
       name="LineageOS/android_vendor_qcom_opensource_audio-hal_st-hal-ar"
       remote="github"
       revision="lineage-24.0" />
<!-- WLAN HAL -->
<project path="hardware/qcom-caf/wlan"
       name="LineageOS/android_hardware_qcom_wlan"
       remote="github"
       revision="lineage-24.0-caf" />
<!-- SEPolicy for sm8450 family -->
<project path="device/qcom/sepolicy_vndr/sm8450"
       name="LineageOS/android_device_qcom_sepolicy_vndr"
       remote="github"
       revision="lineage-24.0-caf-sm8450" />
</manifest>
EOF
```
## Repo Sync
```
Repo Sync
```
## Build
```
. build/envsetup.sh
lunch lineage_m55xq-cp1a-userdebug
mka bacon
```

#
# SPDX-FileCopyrightText: The LineageOS Project
# SPDX-License-Identifier: Apache-2.0
#
#
