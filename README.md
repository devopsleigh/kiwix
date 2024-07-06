# Kiwix

Offline Wiki reader

## Manual steps

1. Ensure the `data` folder is a symlink hosted on external storage
   ```sh
   destination_dir=/mnt/yourappdata/kiwix
   mkdir $destination_dir
   ln -s "$destination_dir" data
   ```
2. Select and download ZIM files of interest from [Kiwix's repository](https://download.kiwix.org/zim/)
   ```sh
   zim_array=("https://download.kiwix.org/zim/wikipedia/wikipedia_en_all_maxi_2024-01.zim" \
   "https://download.kiwix.org/zim/wikipedia/wikipedia_en_medicine_2024-04.zim" \
   "https://download.kiwix.org/zim/gutenberg/gutenberg_en_all_2023-08.zim" \
   "https://download.kiwix.org/zim/zimit/fas-military-medicine_en_2024-06.zim" \
   "https://download.kiwix.org/zim/ifixit/ifixit_en_all_2024-06.zim"
   )
   for url in "${zim_array[@]}"; do
     wget "$url"
   done
   ```

## Updating the library

Run the `update-zim-sh` script. This is a wrapper over jojo2357's `kiwix-zim-updater` script.

<!-- TODO: turn this into a cron job -->
