---
title: "Overview of Aspose Cloud REST API"
type: docs
url: /overview-of-aspose-cloud-rest-api/
weight: 20
---

## **Introduction**
This document outlines the design of a REST-based API for Aspose for Cloud, it covers both the structure of REST URLs as well as specific behavior linked to the API such as Authentication, Request Queuing, and Storage. The Aspose Cloud API will give developers access to all the key functions of the [downloadable Aspose componenets](https://www.aspose.com/) through a Software as a Service hosted model.

There will be 3 sub-components within the API design (although these are largely transparent to the end-user);

- Platform - this covers elements of the Aspose Cloud platform, not directly linked to file format manipulation, such as Storage, Authentication, Queuing, etc;
- Common - this covers common elements of the API which are shared by all products;
- Product - this covers product specific areas for each product;
  - Aspose.Words
  - Aspose.Cells
  - Aspose.Pdf
  - Aspose.Slides
  - Aspose.Email
  - Aspose.BarCode
  - Aspose.Imaging
  - Aspose.Tasks
  - Aspose.OCR
  - Aspose.OMR
## **API Basics**
The Aspose Cloud API is a REST-based API for wide usability on the web across platforms. By default, the REST API returns XML formatted responses, but it is possible to get the response in JSON format by setting Content-Type to **application/json**. Accompanying the REST API will be Client SDKs for all major development platforms which will provide client libraries to make it very easy for developers to code against the Aspose Cloud APIs.
### **Base URL**
Aspose Cloud API requests are made by sending a correctly constructed HTTP requests to the following address, with arguments being generally submitted as **HTTP** **get** or **post** arguments and data files being sent as **HTTP** **post** method where necessary.

```html

https://api.aspose.cloud/\*

```
### **Versions**
Each version beginning with 1.0 will have its number as a part of the URL. So the next URLs are used for the first version:

```html

https://api.aspose.cloud/v1.1/\*

```
### **Routes**
Each product uses its own URL route (key word) to separate its interface:

1. File storage uses **storage** and sub routes **file** and **folder** for files and folders manipulation correspondingly;

```html

https://api.aspose.cloud/v1.1/storage

```

1. Words uses **words** route;

```html

https://api.aspose.cloud/v1.1/words

```

1. Cells uses **cells** route;

```html

https://api.aspose.cloud/v1.1/cells

```

1. Pdf uses **pdf** route;

```html

https://api.aspose.cloud/v1.1/pdf

```

1. Slides uses **slides** route;

```html

https://api.aspose.cloud/v1.1/slides

```

1. Email uses **email** route;

```html

https://api.aspose.cloud/v1.1/email

```

1. BarCode uses **barcode** route;

```html

https://api.aspose.cloud/v1.1/barcode

```

1. Imaging uses **imaging** route;

```html

https://api.aspose.cloud/v1.1/imaging

```

1. Tasks uses **tasks** route;

```html

https://api.aspose.cloud/v1.1/tasks

```

1. OCR uses **ocr** route;

```html

https://api.aspose.cloud/v1.1/ocr

```

1. OMR uses **omr** route;

```html

https://api.aspose.cloud/v1.1/omr

```

Folders

Each user's application has its own root folder at the server, but any number of subfolders at different levels can be created as well. File storage considers folders as resources and gets the folder or file path as a part of URL:

```html

https://api.aspose.cloud/v1.1/folder/subfolder/subsubfolder/file.txt

```


where the file relative to application root folder path is folder/subfolder/subsubfolder/file.txt. See e.g. [Folder]() for additional details.

While product services get the folder path as a query string folder parameter.
### **URI Structure**
Within the API we will have Resources (each identified by a URI) and Operations (as much as possible covered by the 4 HTTP Methods: GET, POST, PUT and DELETE) which can be applied to those resources.

Default 'empty' request <https://api.aspose.cloud/v1.1> redirects to service start page with a link to some helpful examples. Please check following articles for information regarding Request and Response Format and how to authenticate Aspose Cloud API request.

- [Authenticating API Requests](/storage/authenticating-api-requests/)
- [JSON Web Token Authentication](/storage/json-web-token-authentication/)
- [Request Format](/storage/request-format/)
- [Response Format](/storage/response-format/)
