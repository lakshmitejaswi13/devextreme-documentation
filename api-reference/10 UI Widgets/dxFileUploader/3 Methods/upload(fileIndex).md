---
id: dxFileUploader.upload(fileIndex)
---
---
##### shortDescription
Uploads a file with the specified index.

##### param(fileIndex): Number
The file's index.

---

---

##### jQuery

    <!-- tab: JavaScript -->
    var uploadControl = $("#file-uploader").dxFileUploader("instance");

    uploadControl.upload(1);

---

[note]
The **upload** method is not supported in **useForms** [upload mode](/api-reference/10%20UI%20Widgets/dxFileUploader/1%20Configuration/uploadMode.md '/Documentation/ApiReference/UI_Widgets/dxFileUploader/Configuration/#uploadMode'). In **instantly** upload mode, the **upload** method is useful if you use the [value](/api-reference/10%20UI%20Widgets/dxFileUploader/1%20Configuration/value.md '/Documentation/ApiReference/UI_Widgets/dxFileUploader/Configuration/#value') option to select a file(s) you want to upload.