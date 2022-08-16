# Scan Kit

Scan Kit scans, parses, and generates major 1D and 2D barcodes, helping you quickly build barcode scanning functions into your apps.

## Overview

Scan Kit automatically detects, magnifies, and recognizes barcodes from a distance, and is also able to scan a very small barcode in the same way. It works even in suboptimal situations, such as in dim light condition or when the barcode is reflective, dirty, blurry, or printed on a cylindrical surface. This leads to a high scanning success rate, and an improved user experience.

Scan Kit can be integrated into both Android and iOS apps. Android apps with Scan Kit integrated support barcode scanning in landscape mode.


`Use In Project` : 
 
 To get scan result firstly subscribe to ScanSuccess delegate to catch the result callback.

  ```csharp

    private void OnEnable()
    {
        HMSScanKitManager.Instance.ScanSuccess += OnScanSuccess;
    }

    private void OnDisable()
    {
        HMSScanKitManager.Instance.ScanSuccess -= OnScanSuccess;
    }

  ```

To open camera for scanning run the following command.

 ```csharp

    public void Scan()
    {
        HMSScanKitManager.Instance.Scan(HmsScanBase.ALL_SCAN_TYPE);
    }

  ```

At the method that subscribed to ScanSuccess delegate, you can catch the result.

   ```csharp

    private void OnScanSuccess(string text, HmsScan hmsScan)
    {
        Debug.Log("OnScanSuccess");
        
        Txt_QRCode.text = text;
    }

  ```