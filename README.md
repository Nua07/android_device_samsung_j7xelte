# Crdroid

### How to build ###

```bash
# Create dirs
$ mkdir crdroid ; cd crdroid

# Init repo
$ repo init --depth=1 -u https://github.com/crdroidandroid/android.git -b 10.0

# Clone my local repo
$ git clone https://github.com/sasi2006166-exynos7870/local_manifests.git -b crdroid-q .repo/local_manifests

# Sync
$ repo sync --no-repo-verify -c --force-sync --no-clone-bundle --no-tags --optimized-fetch --prune -jx

# Build
$ . build/envsetup.sh && brunch j7xelte
```










