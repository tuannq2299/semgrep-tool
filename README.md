# Semgrep Rule for .NET and Java

![powered by semgrep](https://camo.githubusercontent.com/91db6f03a93b1019684dffd8cc519b00585a12902143fcaa5ccb2333fdc6c068/68747470733a2f2f696d672e736869656c64732e696f2f62616467652f706f776572656425323062792d73656d677265702d3142324633443f6c6162656c436f6c6f723d6c6967687467726579266c696e6b3d68747470733a2f2f73656d677265702e6c6976652f267374796c653d666c61742d737175617265266c6f676f3d64617461253341696d616765253246706e672533426261736536342532436956424f5277304b47676f414141414e5355684555674141414130414141414f43415941414144306635625341414141426d4a4c523051412f67442b41502b63482b5155414141414358424957584d41414133584141414e317746434b4a7434414141414233524a545555483541594d4579306c38646b71725141414176464a524546554b4255423567495a2f514541415038424141414141414d47364144392b686e2f477a412f2f77442f2f7741414141442b41414141416741424151446c304d45424177626d416633364751414141414141415145433951482f2f67762f47693147465145432b4f6f41414141414141414141414142415141412f2f384141414141414141414141442f2f67675835744f363667494439414542465352784167594c7a52514141414470414141414150372b2f67446c30634d50414141412b77414141506b624c7a3339416749434141414141414141414141732b765531324145624c7a34624141414135503841414141412f2f3441354e444445774542414f2f2f2f7741424151454141502f2f414277634d4437684151454241414141414141414141416141674141414f41414141414141514542414f585277785541414144772f2f3841416741414141442f2f77414141414141354f585277686341415145414141414141414141414f4943414141414250332b2f67446a7a7341542f2f384137674141414145414141442b414141412f77414141414141414141412f2f38413765504f77412f2b2f7634414141414142414941414141414141414141414141414f384141414142414141414141414141414941414141424141414141414141414167414141442f4141414138774141414141414141414141674141414141414141414141414141414141414141384141414145414141412f6741414150384141414144414141412f6741414150384141414141414141414141414141414143414141414141414141414141414141414141414137774141415073414141415241414141424141414150344141414141414141414167414141425941414141414141414141414941414144384177494341423079515037382f763447414141412f7741414150414141414439414141412f774141415072392f2f386148544a4136414943416741414141443841674141414449414141414141502f2f414234775076674141414152415145412f67454241503442415141424141414147423076506549412f2f38414141414141414141414241432b76557a31514141414138414141414141774d44414277775075332f2f7741652f2f384141762f2f414241634d44376c41774d444141414141414141414141472b7655302b514542417655422f2f344c2f786f745268554241766a714141414141414141414141414151454141502f2f4141414141414141414141412f2f3449462b625475756f43412f5142415141412f774541414141414177626f41503336476638624d442f2f41502f2f41414141415034414141414341414542414f585177514544427559422f666f5a4141414141414434493671624b332b317a5141414141424a52553545726b4a6767673d3d)

> Semgrep is a fast, open-source, static analysis tool for finding bugs and enforcing code standards at editor, commit, and CI time. [Get started →.](https://github.com/returntocorp/semgrep#getting-started)

This project is a collection of Semgrep rules which followed security guidelines for .NET and Java. Many of these rules have just been tested in a few testcases (mostly provided by Microsoft or Oracle) so they may not work correctly every time. Contact us if you find any bugs in the rule.

References:

- [GitHub / returntocorp / semgrep](https://github.com/returntocorp/semgrep)
- [GitHub / returntocorp / semgrep-rules](https://github.com/returntocorp/semgrep-rules)
- [Security rules for .NET](https://docs.microsoft.com/en-us/dotnet/fundamentals/code-analysis/quality-rules/security-warnings)
- [Secure Coding Guidelines for Java SE](https://www.oracle.com/java/technologies/javase/seccodeguide.html)

## Rules for .NET

| Rule                                                         |     Supported      | Note                                                         | Link                                                         |
| :----------------------------------------------------------- | :----------------: | :----------------------------------------------------------- | ------------------------------------------------------------ |
| [CA2100: Review SQL queries for security vulnerabilities](https://docs.microsoft.com/en-us/dotnet/fundamentals/code-analysis/quality-rules/ca2100) | :heavy_check_mark: |                                                              | [CA2100.yaml](csharp/CA2100.yaml)                            |
| [CA2109: Review visible event handlers](https://docs.microsoft.com/en-us/dotnet/fundamentals/code-analysis/quality-rules/ca2109) | :heavy_check_mark: |                                                              | [CA2109.yaml](csharp/CA2109.yaml)                            |
| [CA2119: Seal methods that satisfy private interfaces](https://docs.microsoft.com/en-us/dotnet/fundamentals/code-analysis/quality-rules/ca2119) | :heavy_check_mark: | May be not working properly because semgrep hasn't supported interface yet (?) | [CA2119.yaml](csharp/CA2119.yaml)                            |
| [CA2153: Avoid Handling Corrupted State Exceptions](https://docs.microsoft.com/en-us/dotnet/fundamentals/code-analysis/quality-rules/ca2153) | :heavy_check_mark: |                                                              | [CA2153.yaml](csharp/CA2153.yaml)                            |
| [CA2300: Do not use insecure deserializer BinaryFormatter](https://docs.microsoft.com/en-us/dotnet/fundamentals/code-analysis/quality-rules/ca2300) | :heavy_check_mark: |                                                              | [CA2300.yaml](csharp/CA2300.yaml)                            |
| [CA2301: Do not call BinaryFormatter.Deserialize without first setting BinaryFormatter.Binder](https://docs.microsoft.com/en-us/dotnet/fundamentals/code-analysis/quality-rules/ca2301) | :heavy_check_mark: |                                                              | [CA2301_2302.yaml](csharp/CA2301_2302.yaml)                  |
| [CA2302: Ensure BinaryFormatter.Binder is set before calling BinaryFormatter.Deserialize](https://docs.microsoft.com/en-us/dotnet/fundamentals/code-analysis/quality-rules/ca2302) | :heavy_check_mark: | Merge with CA2301                                            | [CA2301_2302.yaml](csharp/CA2301_2302.yaml)                  |
| [CA2305: Do not use insecure deserializer LosFormatter](https://docs.microsoft.com/en-us/dotnet/fundamentals/code-analysis/quality-rules/ca2305) | :heavy_check_mark: |                                                              | [CA2305.yaml](csharp/CA2305.yaml)                            |
| [CA2310: Do not use insecure deserializer NetDataContractSerializer](https://docs.microsoft.com/en-us/dotnet/fundamentals/code-analysis/quality-rules/ca2310) | :heavy_check_mark: |                                                              | [CA2310.yaml](csharp/CA2310.yaml)                            |
| [CA2311: Do not deserialize without first setting NetDataContractSerializer.Binder](https://docs.microsoft.com/en-us/dotnet/fundamentals/code-analysis/quality-rules/ca2311) | :heavy_check_mark: |                                                              | [CA2311_2312.yaml](csharp/CA2311_2312.yaml)                  |
| [CA2312: Ensure NetDataContractSerializer.Binder is set before deserializing](https://docs.microsoft.com/en-us/dotnet/fundamentals/code-analysis/quality-rules/ca2312) | :heavy_check_mark: | Merge with CA2311                                            | [CA2311_2312.yaml](csharp/CA2311_2312.yaml)                  |
| [CA2315: Do not use insecure deserializer ObjectStateFormatter](https://docs.microsoft.com/en-us/dotnet/fundamentals/code-analysis/quality-rules/ca2315) | :heavy_check_mark: |                                                              | [CA2315.yaml](csharp/CA2315.yaml)                            |
| [CA2321: Do not deserialize with JavaScriptSerializer using a SimpleTypeResolver](https://docs.microsoft.com/en-us/dotnet/fundamentals/code-analysis/quality-rules/ca2321) | :heavy_check_mark: |                                                              | [CA2321_2322.yaml](csharp/CA2321_2322.yaml)                  |
| [CA2322: Ensure JavaScriptSerializer is not initialized with SimpleTypeResolver before deserializing](https://docs.microsoft.com/en-us/dotnet/fundamentals/code-analysis/quality-rules/ca2322) | :heavy_check_mark: | Merge with CA2321                                            | [CA2321_2322.yaml](csharp/CA2321_2322.yaml)                  |
| [CA2326: Do not use TypeNameHandling values other than None](https://docs.microsoft.com/en-us/dotnet/fundamentals/code-analysis/quality-rules/ca2326) | :heavy_check_mark: |                                                              | [CA2326.yaml](csharp/CA2326.yaml)                            |
| [CA2327: Do not use insecure JsonSerializerSettings](https://docs.microsoft.com/en-us/dotnet/fundamentals/code-analysis/quality-rules/ca2327) | :heavy_check_mark: |                                                              | [CA2327_2328.yaml](csharp/CA2327_2328.yaml)                  |
| [CA2328: Ensure that JsonSerializerSettings are secure](https://docs.microsoft.com/en-us/dotnet/fundamentals/code-analysis/quality-rules/ca2328) | :heavy_check_mark: | Merge with CA2327                                            | [CA2327_2328.yaml](csharp/CA2327_2328.yaml)                  |
| [CA2329: Do not deserialize with JsonSerializer using an insecure configuration](https://docs.microsoft.com/en-us/dotnet/fundamentals/code-analysis/quality-rules/ca2329) | :heavy_check_mark: |                                                              | [CA2329_2330.yaml](csharp/CA2329_2330.yaml)                  |
| [CA2330: Ensure that JsonSerializer has a secure configuration when deserializing](https://docs.microsoft.com/en-us/dotnet/fundamentals/code-analysis/quality-rules/ca2330) | :heavy_check_mark: | Merge with CA2329                                            | [CA2329_2330.yaml](csharp/CA2329_2330.yaml)                  |
| [CA2350: Ensure DataTable.ReadXml()'s input is trusted](https://docs.microsoft.com/en-us/dotnet/fundamentals/code-analysis/quality-rules/ca2350) | :heavy_check_mark: |                                                              | [CA2350.yaml](csharp/CA2350.yaml)                            |
| [CA2351: Ensure DataSet.ReadXml()'s input is trusted](https://docs.microsoft.com/en-us/dotnet/fundamentals/code-analysis/quality-rules/ca2351) | :heavy_check_mark: |                                                              | [CA2351.yaml](csharp/CA2351.yaml)                            |
| [CA2352: Unsafe DataSet or DataTable in serializable type can be vulnerable to remote code execution attacks](https://docs.microsoft.com/en-us/dotnet/fundamentals/code-analysis/quality-rules/ca2352) |        :x:         | Semgrep haven't supported class definitions for C#           |                                                              |
| [CA2353: Unsafe DataSet or DataTable in serializable type](https://docs.microsoft.com/en-us/dotnet/fundamentals/code-analysis/quality-rules/ca2353) |        :x:         | Semgrep haven't supported class definitions for C#           |                                                              |
| [CA2354: Unsafe DataSet or DataTable in deserialized object graph can be vulnerable to remote code execution attack](https://docs.microsoft.com/en-us/dotnet/fundamentals/code-analysis/quality-rules/ca2354) |        :x:         | Semgrep haven't supported class definitions for C#, but can combine rules about insecure deserialization above |                                                              |
| [CA2355: Unsafe DataSet or DataTable in deserialized object graph](https://docs.microsoft.com/en-us/dotnet/fundamentals/code-analysis/quality-rules/ca2355) |        :x:         | Semgrep haven't supported class definitions for C#, but can combine rules about insecure deserialization above |                                                              |
| [CA2356: Unsafe DataSet or DataTable in web deserialized object graph](https://docs.microsoft.com/en-us/dotnet/fundamentals/code-analysis/quality-rules/ca2356) | :heavy_check_mark: |                                                              | [CA2356.yaml](csharp/CA2356.yaml)                            |
| [CA2361: Ensure autogenerated class containing DataSet.ReadXml() is not used with untrusted data](https://docs.microsoft.com/en-us/dotnet/fundamentals/code-analysis/quality-rules/ca2361) | :heavy_check_mark: |                                                              | [CA2361.yaml](csharp/CA2361.yaml)                            |
| [CA2362: Unsafe DataSet or DataTable in autogenerated serializable type can be vulnerable to remote code execution attacks](https://docs.microsoft.com/en-us/dotnet/fundamentals/code-analysis/quality-rules/ca2362) |        :x:         | Semgrep haven't supported class definitions for C#           |                                                              |
| [CA3001: Review code for SQL injection vulnerabilities](https://docs.microsoft.com/en-us/dotnet/fundamentals/code-analysis/quality-rules/ca3001) | :heavy_check_mark: |                                                              | [CA3001.yaml](csharp/CA3001.yaml)                            |
| [CA3002: Review code for XSS vulnerabilities](https://docs.microsoft.com/en-us/dotnet/fundamentals/code-analysis/quality-rules/ca3002) | :heavy_check_mark: |                                                              | [CA3002.yaml](csharp/CA3002.yaml)                            |
| [CA3003: Review code for file path injection vulnerabilities](https://docs.microsoft.com/en-us/dotnet/fundamentals/code-analysis/quality-rules/ca3003) | :heavy_check_mark: |                                                              | [CA3003.yaml](csharp/CA3003.yaml)                            |
| [CA3004: Review code for information disclosure vulnerabilities](https://docs.microsoft.com/en-us/dotnet/fundamentals/code-analysis/quality-rules/ca3004) | :heavy_check_mark: |                                                              |                                                              |
| [CA3006: Review code for process command injection vulnerabilities](https://docs.microsoft.com/en-us/dotnet/fundamentals/code-analysis/quality-rules/ca3006) | :heavy_check_mark: |                                                              |                                                              |
| [CA3007: Review code for open redirect vulnerabilities](https://docs.microsoft.com/en-us/dotnet/fundamentals/code-analysis/quality-rules/ca3007) | :heavy_check_mark: |                                                              |                                                              |
| [CA3008: Review code for XPath injection vulnerabilities](https://docs.microsoft.com/en-us/dotnet/fundamentals/code-analysis/quality-rules/ca3008) | :heavy_check_mark: |                                                              |                                                              |
| [CA3009: Review code for XML injection vulnerabilities](https://docs.microsoft.com/en-us/dotnet/fundamentals/code-analysis/quality-rules/ca3009) | :heavy_check_mark: |                                                              |                                                              |
| [CA3010: Review code for XAML injection vulnerabilities](https://docs.microsoft.com/en-us/dotnet/fundamentals/code-analysis/quality-rules/ca3010) | :heavy_check_mark: |                                                              |                                                              |
| [CA3011: Review code for DLL injection vulnerabilities](https://docs.microsoft.com/en-us/dotnet/fundamentals/code-analysis/quality-rules/ca3011) | :heavy_check_mark: |                                                              |                                                              |
| [CA3012: Review code for regex injection vulnerabilities](https://docs.microsoft.com/en-us/dotnet/fundamentals/code-analysis/quality-rules/ca3012) | :heavy_check_mark: |                                                              |                                                              |
| [CA3061: Do not add schema by URL](https://docs.microsoft.com/en-us/dotnet/fundamentals/code-analysis/quality-rules/ca3061) | :heavy_check_mark: |                                                              |                                                              |
| [CA3075: Insecure DTD Processing](https://docs.microsoft.com/en-us/dotnet/fundamentals/code-analysis/quality-rules/ca3075) | :heavy_check_mark: |                                                              |                                                              |
| [CA3076: Insecure XSLT Script Execution](https://docs.microsoft.com/en-us/dotnet/fundamentals/code-analysis/quality-rules/ca3076) | :heavy_check_mark: |                                                              |                                                              |
| [CA3077: Insecure Processing in API Design, XML Document and XML Text Reader](https://docs.microsoft.com/en-us/dotnet/fundamentals/code-analysis/quality-rules/ca3077) | :heavy_check_mark: |                                                              |                                                              |
| [CA3147: Mark verb handlers with ValidateAntiForgeryToken](https://docs.microsoft.com/en-us/dotnet/fundamentals/code-analysis/quality-rules/ca3147) |                    |                                                              |                                                              |
| [CA5350: Do Not Use Weak Cryptographic Algorithms](https://docs.microsoft.com/en-us/dotnet/fundamentals/code-analysis/quality-rules/ca5350) | :heavy_check_mark: |                                                              |                                                              |
| [CA5351: Do Not Use Broken Cryptographic Algorithms](https://docs.microsoft.com/en-us/dotnet/fundamentals/code-analysis/quality-rules/ca5351) | :heavy_check_mark: |                                                              |                                                              |
| [CA5358: Do Not Use Unsafe Cipher Modes](https://docs.microsoft.com/en-us/dotnet/fundamentals/code-analysis/quality-rules/ca5358) | :heavy_check_mark: |                                                              |                                                              |
| [CA5359: Do not disable certificate validation](https://docs.microsoft.com/en-us/dotnet/fundamentals/code-analysis/quality-rules/ca5359) | :heavy_check_mark: |                                                              |                                                              |
| [CA5360: Do not call dangerous methods in deserialization](https://docs.microsoft.com/en-us/dotnet/fundamentals/code-analysis/quality-rules/ca5360) | :heavy_check_mark: |                                                              |                                                              |
| [CA5361: Do not disable SChannel use of strong crypto](https://docs.microsoft.com/en-us/dotnet/fundamentals/code-analysis/quality-rules/ca5361) |                    |                                                              |                                                              |
| [CA5362: Potential reference cycle in deserialized object graph](https://docs.microsoft.com/en-us/dotnet/fundamentals/code-analysis/quality-rules/ca5362) |                    |                                                              |                                                              |
| [CA5363: Do not disable request validation](https://docs.microsoft.com/en-us/dotnet/fundamentals/code-analysis/quality-rules/ca5363) |                    |                                                              |                                                              |
| [CA5364: Do not use deprecated security protocols](https://docs.microsoft.com/en-us/dotnet/fundamentals/code-analysis/quality-rules/ca5364) |                    |                                                              |                                                              |
| [CA5365: Do Not Disable HTTP Header Checking](https://docs.microsoft.com/en-us/dotnet/fundamentals/code-analysis/quality-rules/ca5365) |                    |                                                              |                                                              |
| [CA5366: Use XmlReader For DataSet Read XML](https://docs.microsoft.com/en-us/dotnet/fundamentals/code-analysis/quality-rules/ca5366) |                    |                                                              |                                                              |
| [CA5367: Do Not Serialize Types With Pointer Fields](https://docs.microsoft.com/en-us/dotnet/fundamentals/code-analysis/quality-rules/ca5367) |                    |                                                              |                                                              |
| [CA5368: Set ViewStateUserKey For Classes Derived From Page](https://docs.microsoft.com/en-us/dotnet/fundamentals/code-analysis/quality-rules/ca5368) |                    |                                                              |                                                              |
| [CA5369: Use XmlReader for Deserialize](https://docs.microsoft.com/en-us/dotnet/fundamentals/code-analysis/quality-rules/ca5369) |                    |                                                              |                                                              |
| [CA5370: Use XmlReader for validating reader](https://docs.microsoft.com/en-us/dotnet/fundamentals/code-analysis/quality-rules/ca5370) |                    |                                                              |                                                              |
| [CA5371: Use XmlReader for schema read](https://docs.microsoft.com/en-us/dotnet/fundamentals/code-analysis/quality-rules/ca5371) |                    |                                                              |                                                              |
| [CA5372: Use XmlReader for XPathDocument](https://docs.microsoft.com/en-us/dotnet/fundamentals/code-analysis/quality-rules/ca5372) |                    |                                                              |                                                              |
| [CA5373: Do not use obsolete key derivation function](https://docs.microsoft.com/en-us/dotnet/fundamentals/code-analysis/quality-rules/ca5373) |                    |                                                              |                                                              |
| [CA5374: Do Not Use XslTransform](https://docs.microsoft.com/en-us/dotnet/fundamentals/code-analysis/quality-rules/ca5374) | :heavy_check_mark: |                                                              | [CA5374.yaml](csharp/CA5374.yaml)                            |
| [CA5375: Do not use account shared access signature](https://docs.microsoft.com/en-us/dotnet/fundamentals/code-analysis/quality-rules/ca5375) | :heavy_check_mark: |                                                              | [CA5375.yaml](csharp/CA5375.yaml)                            |
| [CA5376: Use SharedAccessProtocol HttpsOnly](https://docs.microsoft.com/en-us/dotnet/fundamentals/code-analysis/quality-rules/ca5376) | :heavy_check_mark: |                                                              | [CA5376.yaml](csharp/CA5376.yaml)                            |
| [CA5377: Use container level access policy](https://docs.microsoft.com/en-us/dotnet/fundamentals/code-analysis/quality-rules/ca5377) | :heavy_check_mark: |                                                              | [CA5377.yaml](csharp/CA5377.yaml)                            |
| [CA5378: Do not disable ServicePointManagerSecurityProtocols](https://docs.microsoft.com/en-us/dotnet/fundamentals/code-analysis/quality-rules/ca5378) | :heavy_check_mark: |                                                              | [CA5378.yaml](csharp/CA5378.yaml)                            |
| [CA5379: Ensure key derivation function algorithm is sufficiently strong](https://docs.microsoft.com/en-us/dotnet/fundamentals/code-analysis/quality-rules/ca5379) | :heavy_check_mark: |                                                              | [CA5379.yaml](csharp/CA5379.yaml)                            |
| [CA5380: Do not add certificates to root store](https://docs.microsoft.com/en-us/dotnet/fundamentals/code-analysis/quality-rules/ca5380) | :heavy_check_mark: |                                                              | [CA5380.yaml](csharp/CA5380.yaml)                            |
| [CA5381: Ensure certificates are not added to root store](https://docs.microsoft.com/en-us/dotnet/fundamentals/code-analysis/quality-rules/ca5381) | :heavy_check_mark: |                                                              | [CA5381.yaml](csharp/CA5381.yaml)                            |
| [CA5382: Use secure cookies in ASP.NET Core](https://docs.microsoft.com/en-us/dotnet/fundamentals/code-analysis/quality-rules/ca5382) | :heavy_check_mark: |                                                              | [CA5382.yaml](csharp/CA5382.yaml)                            |
| [CA5383: Ensure use secure cookies in ASP.NET Core](https://docs.microsoft.com/en-us/dotnet/fundamentals/code-analysis/quality-rules/ca5383) | :heavy_check_mark: |                                                              | [CA5383.yaml](csharp/CA5383.yaml)                            |
| [CA5384: Do not use digital signature algorithm (DSA)](https://docs.microsoft.com/en-us/dotnet/fundamentals/code-analysis/quality-rules/ca5384) | :heavy_check_mark: |                                                              | [CA5384.yaml](csharp/CA5384.yaml)                            |
| [CA5385: Use Rivest–Shamir–Adleman (RSA) algorithm with sufficient key size](https://docs.microsoft.com/en-us/dotnet/fundamentals/code-analysis/quality-rules/ca5385) | :heavy_check_mark: | Separate into 2 rule: CA5385_1 and CA5385_2                  | [CA5385_1.yaml](csharp/CA5385_1.yaml) [CA5385_2.yaml](csharp/CA5385_2.yaml) |
| [CA5386: Avoid hardcoding SecurityProtocolType value](https://docs.microsoft.com/en-us/dotnet/fundamentals/code-analysis/quality-rules/ca5386) | :heavy_check_mark: |                                                              | [CA5386.yaml](csharp/CA5386.yaml)                            |
| [CA5387: Do not use weak key derivation function with insufficient iteration count](https://docs.microsoft.com/en-us/dotnet/fundamentals/code-analysis/quality-rules/ca5387) | :heavy_check_mark: |                                                              | [CA5387.yaml](csharp/CA5387.yaml)                            |
| [CA5388: Ensure sufficient iteration count when using weak key derivation function](https://docs.microsoft.com/en-us/dotnet/fundamentals/code-analysis/quality-rules/ca5388) | :heavy_check_mark: |                                                              | [CA5388.yaml](csharp/CA5388.yaml)                            |
| [CA5389: Do not add archive item's path to the target file system path](https://docs.microsoft.com/en-us/dotnet/fundamentals/code-analysis/quality-rules/ca5389) | :heavy_check_mark: |                                                              | [CA5389.yaml](csharp/CA5389.yaml)                            |
| [CA5390: Do not hard-code encryption key](https://docs.microsoft.com/en-us/dotnet/fundamentals/code-analysis/quality-rules/ca5390) | :heavy_check_mark: | Separate into 2 rule: CA5390_1 and CA5390_2                  | [CA5390_1.yaml](csharp/CA5390_1.yaml) [CA5390_2.yaml](csharp/CA5390_2.yaml) |
| [CA5391: Use antiforgery tokens in ASP.NET Core MVC controllers](https://docs.microsoft.com/en-us/dotnet/fundamentals/code-analysis/quality-rules/ca5391) | :heavy_check_mark: |                                                              | [CA5391.yaml](csharp/CA5391.yaml)                            |
| [CA5392: Use DefaultDllImportSearchPaths attribute for P/Invokes](https://docs.microsoft.com/en-us/dotnet/fundamentals/code-analysis/quality-rules/ca5392) | :heavy_check_mark: |                                                              | [CA5392.yaml](csharp/CA5392.yaml)                            |
| [CA5393: Do not use unsafe DllImportSearchPath value](https://docs.microsoft.com/en-us/dotnet/fundamentals/code-analysis/quality-rules/ca5393) | :heavy_check_mark: |                                                              | [CA5393.yaml](csharp/CA5393.yaml)                            |
| [CA5394: Do not use insecure randomness](https://docs.microsoft.com/en-us/dotnet/fundamentals/code-analysis/quality-rules/ca5394) | :heavy_check_mark: |                                                              | [CA5394.yaml](csharp/CA5394.yaml)                            |
| [CA5395: Miss HttpVerb attribute for action methods](https://docs.microsoft.com/en-us/dotnet/fundamentals/code-analysis/quality-rules/ca5395) | :heavy_check_mark: |                                                              | [CA5395.yaml](csharp/CA5395.yaml)                            |
| [CA5396: Set HttpOnly to true for HttpCookie](https://docs.microsoft.com/en-us/dotnet/fundamentals/code-analysis/quality-rules/ca5396) | :heavy_check_mark: |                                                              | [CA5396.yaml](csharp/CA5396.yaml)                            |
| [CA5397: Do not use deprecated SslProtocols values](https://docs.microsoft.com/en-us/dotnet/fundamentals/code-analysis/quality-rules/ca5397) | :heavy_check_mark: |                                                              | [CA5397.yaml](csharp/CA5397.yaml)                            |
| [CA5398: Avoid hardcoded SslProtocols values](https://docs.microsoft.com/en-us/dotnet/fundamentals/code-analysis/quality-rules/ca5398) | :heavy_check_mark: |                                                              | [CA5398.yaml](csharp/CA5398.yaml)                            |
| [CA5399: Definitely disable HttpClient certificate revocation list check](https://docs.microsoft.com/en-us/dotnet/fundamentals/code-analysis/quality-rules/ca5399) | :heavy_check_mark: |                                                              | [CA5399.yaml](csharp/CA5399.yaml)                            |
| [CA5400: Ensure HttpClient certificate revocation list check is not disabled](https://docs.microsoft.com/en-us/dotnet/fundamentals/code-analysis/quality-rules/ca5400) | :heavy_check_mark: |                                                              | [CA5400.yaml](csharp/CA5400.yaml)                            |
| [CA5401: Do not use CreateEncryptor with non-default IV](https://docs.microsoft.com/en-us/dotnet/fundamentals/code-analysis/quality-rules/ca5401) | :heavy_check_mark: |                                                              | [CA5401.yaml](csharp/CA5401.yaml)                            |
| [CA5402: Use CreateEncryptor with the default IV](https://docs.microsoft.com/en-us/dotnet/fundamentals/code-analysis/quality-rules/ca5402) | :heavy_check_mark: |                                                              | [CA5402.yaml](csharp/CA5402.yaml)                            |
| [CA5403: Do not hard-code certificate](https://docs.microsoft.com/en-us/dotnet/fundamentals/code-analysis/quality-rules/ca5403) | :heavy_check_mark: |                                                              | [CA5403.yaml](csharp/CA5403.yaml)                            |
| [CA5404: Do not disable token validation checks](https://docs.microsoft.com/en-us/dotnet/fundamentals/code-analysis/quality-rules/ca5404) | :heavy_check_mark: |                                                              | [CA5404.yaml](csharp/CA5404.yaml)                            |
| [CA5405: Do not always skip token validation in delegates](https://docs.microsoft.com/en-us/dotnet/fundamentals/code-analysis/quality-rules/ca5405) | :heavy_check_mark: |                                                              | [CA5405.yaml](csharp/CA5405.yaml)                            |

## Rules for Java
