Device configuration for the Samsung Galaxy J7 2016

Copyright (C) 2017 The LineageOS Project
Copyright (C) 2017 Valera Chigir <valera1978@tut.by>
Copyright (C) 2019 Salvatore Fornaro

 Licensed under the Apache License, Version 2.0 (the "License");
 you may not use this file except in compliance with the License.
 You may obtain a copy of the License at

      http://www.apache.org/licenses/LICENSE-2.0

------------------------------------------------------------------

* Description

  This repository is for LineageOS on Samsung Galaxy J7 2016 (j7xelte)

* How To Build LineageOS for Samsung Galaxy J7 2016

  - Make a workspace

mkdir LineageOS
cd LineageOS

  - Do repo init & sync

repo init -u git://github.com/LineageOS/android.git -b lineage-17.0
repo init -u git://github.com/crdroidandroid/android.git -b 10.0

  - Create .repo/local_manifests/roomservice.xml with the following content:

```
<?xml version="1.0" encoding="UTF-8"?>
<manifest>

  <project name="sasi2006166-exynos7870/android_device_samsung_j7xelte" path="device/samsung/j7xelte" remote="github" />
  <project name="sasi2006166-exynos7870/android_kernel_samsung_exynos7870" path="kernel/samsung/exynos7870" remote="github" />
  <project name="sasi2006166-exynos7870/android_vendor_samsung_j7xelte" path="vendor/samsung/j7xelte" remote="github" />

  <project name="Valera1978/android_hardware_samsung" path="hardware/samsung" remote="github" />
  <project name="LineageOS/android_packages_resources_devicesettings" path="packages/resources/devicesettings" remote="github" />

</manifest>
```

repo sync

  - Copy proprietary vendor files

  There are two options to to that. Connect your device with adb enabled and run:

./extract-files.sh

  Or if you have the system image unpacked on your disk, then simply run:

    STOCK_ROM_DIR=/path/to/system ./extract-files.sh

  - Setup environment

. build/envsetup.sh

  - Build LineageOS

brunch j7xelte
