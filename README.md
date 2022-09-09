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






  # APM

App Performance Management (APM) of AppGallery Connect is a powerful yet easy-to-use tool that offers solutions to app performance management.

## Overview

Enhanced functions: track performance data of a running app on each device, helping you quickly detect, locate, and resolve app performance issues, including slow app launches, prolonged page loading, ANRs, and delayed network responses. These functions can help you ensure smooth running of your app to improve user experience.
APM allows you to access highly readable reports from AGC in real time without needing to write any code.


`Use In Project` : 

To enable APM.

 ```csharp

    public void APMSCollectionOn()
    {
        Debug.Log(TAG + "APMSCollectionOn");

        HMSAPMManager.Instance.EnableCollection(true);
    }

  ```

To enable monitor ANR.

   ```csharp

    public void APMSAnrMonitorOn()
    {
        Debug.Log(TAG + "APMSAnrMonitorOn");

        HMSAPMManager.Instance.EnableAnrMonitor(true);
    }

  ```