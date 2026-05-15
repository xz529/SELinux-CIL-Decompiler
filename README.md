# DumprX SEPolicy (GitHub Actions)

A universal automation tool powered by GitHub Actions that utilizes `decompile_cil` for automatic extraction of sepolicy from firmware dumps.

The project has been completely decoupled from specific custom ROM repositories (like LineageOS trees) and uses smart, recursive search algorithms, making it fully compatible with raw firmware dumps of any Android device.

## 📌 Features

The script automatically scans the structure of the provided firmware dump, searching for and collecting scattered SELinux policy components and contexts across all available partitions:
* `/system`
* `/vendor`
* `/product`
* `/system_ext`
* `/odm`

Once all `.cil` files and security contexts are detected and organized, the tool executes `decompile_cil` for automatic extraction of sepolicy from the dump. It reverses compiled configuration binaries back into clean, human-readable `.te` policy files—perfect for analyzing, fixing SELinux denials (`avc: denied`), or using in custom ROM development.

## 🚀 How to Use

1. Navigate to the **Actions** tab in your GitHub repository.
2. Select the **DumprX SEPolicy** workflow from the left sidebar.
3. Click the **Run workflow** dropdown button on the right.
4. Paste the Git URL of your firmware dump repository into the input field.
5. Click the green **Run workflow** button.
6. Once the build finishes, download the final `.te` files package from the **Artifacts** section at the bottom of the page.
7. 
