## Create a Swap File (e.g., 8GB)
```sh
sudo fallocate -l 8G /swapfile
```

### If `fallocate` is not available, use:
```sh
sudo dd if=/dev/zero of=/swapfile bs=1M count=8192
```

## Set Proper Permissions
```sh
sudo chmod 600 /swapfile
```

## Format as Swap
```sh
sudo mkswap /swapfile
```

## Enable the Swap
```sh
sudo swapon /swapfile
```

## Make Swap Persistent
Add the following line to `/etc/fstab`:
```sh
echo '/swapfile none swap sw 0 0' | sudo tee -a /etc/fstab
