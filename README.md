# openapi-java-client

Screenshot Capture API
- API version: 1.0.0
  - Build date: 2021-08-22T18:58:01.482+02:00[Europe/Berlin]

screenshot-capture-api.com Screenshot Capture is a very simple but powerful screenshot API that anyone can easily use to create pixel-perfect website screenshots. It always uses a recent version of Chrome to ensure that all modern web features are fully supported and rendering is exactly as your customers would expect.


*Automatically generated by the [OpenAPI Generator](https://openapi-generator.tech)*


## Requirements

Building the API client library requires:
1. Java 1.7+
2. Maven/Gradle

## Installation

To install the API client library to your local Maven repository, simply execute:

```shell
mvn clean install
```

To deploy it to a remote Maven repository instead, configure the settings of the repository and execute:

```shell
mvn clean deploy
```

Refer to the [OSSRH Guide](http://central.sonatype.org/pages/ossrh-guide.html) for more information.

### Maven users

Add this dependency to your project's POM:

```xml
<dependency>
  <groupId>org.openapitools</groupId>
  <artifactId>openapi-java-client</artifactId>
  <version>1.0.0</version>
  <scope>compile</scope>
</dependency>
```

### Gradle users

Add this dependency to your project's build file:

```groovy
compile "org.openapitools:openapi-java-client:1.0.0"
```

### Others

At first generate the JAR by executing:

```shell
mvn clean package
```

Then manually install the following JARs:

* `target/openapi-java-client-1.0.0.jar`
* `target/lib/*.jar`

## Getting Started

Please follow the [installation](#installation) instruction and execute the following Java code:

```java

// Import classes:
import org.openapitools.client.ApiClient;
import org.openapitools.client.ApiException;
import org.openapitools.client.Configuration;
import org.openapitools.client.models.*;
import org.openapitools.client.api.ScreenshotApi;

public class Example {
  public static void main(String[] args) {
    ApiClient defaultClient = Configuration.getDefaultApiClient();
    defaultClient.setBasePath("https://api.screenshot-capture-api.com/v1");

    ScreenshotApi apiInstance = new ScreenshotApi(defaultClient);
    String token = "token_example"; // String | A valid token is needed to make paid API calls. Tokens can be managed from your account.
    String hash = "hash_example"; // String | The hash value is for authenticated requests. If you want to publish this URL, you should use the authenticated requests.
    String url = "url_example"; // String | The URL of the website you want to capture. Please include the protocol (http:// or https://).
    String fileType = "fileType_example"; // String | The image file format of the captured screenshot. Either png, jpeg or PDF with 72 dpi.
    Long ttl = 56L; // Long | Number of seconds the capture file is cached by our CDN. An API request that is loaded through the cache does not count as a paid request. You can set a number of seconds from 0 seconds up to 2592000 seconds. This is a maximum of 30 days.
    Boolean invalidate = true; // Boolean | Force the API to invalidate the cache and capture a new screenshot. This call costs you additional money, because a call of a cache hit is not charged.
    Boolean full = true; // Boolean | Set this parameter to true if you want to screenshot the whole web page in full size.
    Boolean lazyloadScroll = false; // Boolean | Set this parameter to true to scroll down through the entire page before taking a screenshot. This is useful for triggering animations or lazy load elements in full screen.
    Long delay = 56L; // Long | The delay in milliseconds to wait after the page loads before taking the screenshot. This is in milliseconds. One second is 1000 milliseconds. From 0 milliseconds to a maximum of 10,000 milliseconds.
    Long width = 1920L; // Long | The width, in pixels, of the browser viewport to use.
    Long height = 1080L; // Long | The height, in pixels, of the browser viewport to use. Ignored if you set full to true.
    Long quality = 90L; // Long | The quality of the image between 0 and 100. This works only for the jpeg format, for PNG images the parameter is applied only during compression.
    BigDecimal scale = new BigDecimal(78); // BigDecimal | The scale factor of the device to use when taking the screenshot. For example, a scale factor of 2 produces a high-resolution screenshot suitable for viewing on Retina devices. The larger the scale factor, the larger the screenshot produced.
    Long x = 0L; // Long | The starting point of a section screenshot on the X axis.
    Long y = 0L; // Long | The starting point of a section screenshot on the Y axis.
    Boolean redirect = false; // Boolean | If you set Redirect, the response will be a 302 redirect to the screenshot file in our CDN.
    String language = "language_example"; // String | Sets the Accept-Language header on requests to the target URL so that you can take screenshots from a website with a specific language.
    Boolean randomUserAgent = false; // Boolean | Sets a random user agent header to emulate a different devices when taking screenshots.
    String userAgent = "userAgent_example"; // String | Sets the user agent header to emulate a specific device when taking screenshots.
    String headers = "headers_example"; // String | A semicolon-separated list of header parameters to be used when capturing the screenshot. Each header should be passed as a key-value pair and multiple pairs should be separated by a semicolon.
    String cookies = "cookies_example"; // String | A semicolon-separated list of cookies to be used when capturing the screenshot. Each cookies should be passed as a key-value pair and multiple pairs should be separated by a semicolon.
    String css = "css_example"; // String | Inject your custom CSS.
    String js = "js_example"; // String | Inject your custom Javascript.
    String wait = "wait_example"; // String | Wait until the specified CSS selector matches an element present in the page before taking a screenshot. The process is canceled after 60 seconds.
    String element = "element_example"; // String | Takes a screenshot of the first element matched by the specified CSS selector. This is ignored if full is true. (This option cannot be used with the PDF export format.)
    String timezone = "Europe/Berlin"; // String | The IANA time zone identifier used for this capture.
    String device = "device_example"; // String | The device used in the emulation.
    BigDecimal latitude = new BigDecimal(78); // BigDecimal | The latitude used in the emulation of the geo-location.
    BigDecimal longitude = new BigDecimal(78); // BigDecimal | The longitude used in the emulation of the geo-location.
    BigDecimal accuracy = new BigDecimal(78); // BigDecimal | The accuracy in meters used in the emulation of the geo-location.
    String proxy = "proxy_example"; // String | Use an address of a proxy server through which the screenshot should be taken. The proxy address should be formatted as http://username:password@proxyserver.com:31280
    Boolean adblock = false; // Boolean | Prevent ads from being displayed. Block requests from popular ad networks and hide frequent ads.
    Boolean hideCookieBanners = false; // Boolean | Prevent cookie banners and pop-ups from being displayed. The best possible result is tried.
    try {
      File result = apiInstance.captureScreenshotAuthenticated(token, hash, url, fileType, ttl, invalidate, full, lazyloadScroll, delay, width, height, quality, scale, x, y, redirect, language, randomUserAgent, userAgent, headers, cookies, css, js, wait, element, timezone, device, latitude, longitude, accuracy, proxy, adblock, hideCookieBanners);
      System.out.println(result);
    } catch (ApiException e) {
      System.err.println("Exception when calling ScreenshotApi#captureScreenshotAuthenticated");
      System.err.println("Status code: " + e.getCode());
      System.err.println("Reason: " + e.getResponseBody());
      System.err.println("Response headers: " + e.getResponseHeaders());
      e.printStackTrace();
    }
  }
}

```

## Documentation for API Endpoints

All URIs are relative to *https://api.screenshot-capture-api.com/v1*

Class | Method | HTTP request | Description
------------ | ------------- | ------------- | -------------
*ScreenshotApi* | [**captureScreenshotAuthenticated**](docs/ScreenshotApi.md#captureScreenshotAuthenticated) | **GET** /capture/{token}/{hash} | 
*ScreenshotApi* | [**captureScreenshotUnauthenticated**](docs/ScreenshotApi.md#captureScreenshotUnauthenticated) | **GET** /capture/{token} | 


## Documentation for Models

 - [ErrorModel](docs/ErrorModel.md)


## Documentation for Authorization

All endpoints do not require authorization.
Authentication schemes defined for the API:

## Recommendation

It's recommended to create an instance of `ApiClient` per thread in a multithreaded environment to avoid any potential issues.

## Author



