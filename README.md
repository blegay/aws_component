# aws_component
This 4D component enable to interact with AWS and more specifically S3.
The component has been written in 4D v14.
The demo is written in 4D v15.x

[https://www.linkedin.com/in/brunolegay]


     CREATION : Bruno LEGAY (BLE) - 03/01/2016, 13:53:50 - v0.9.00
     MODIFICATION : Bruno LEGAY (BLE) - 25/02/2016, 10:25:01 - v0.9.03
      - added AWS__endpointGet, AWS__serviceList AWS__serviceRegionList
      - and updated AWS_restApi and AWS_authQueryUrl
     MODIFICATION : Bruno LEGAY (BLE) - 03/03/2016, 20:22:56 - v0.9.04
      - allow empty request body or nil for AWS_restApi (#Keith)
     MODIFICATION : Bruno LEGAY (BLE) - 02/03/2016, 18:45:12 - v0.9.05
      - added query string sort for canonical request (AWS__canonicalQueryStrSort)
     MODIFICATION : Bruno LEGAY (BLE) - 17/04/2016, 19:18:23 - v1.0.00
      - renames AWS_restApi into S3_restApi and removed "$1" parameter
      - fixed bugs in sorting query parameters and headers (4D sort is case sensitive, AWS is not case sensitive). See TAB_sortArrayCaseSensitive, TAB_sortArrayMultiCaseSensitive (php, 4D v14-json)
      - fixed potential bugs in uri encoding (improved compliance to AWS specs). see S3_uriEncode
      - refactoring
      - AWS_testCases
      - fixed a bug in S3_restApi when using empty "Content-Type"
     MODIFICATION : Bruno LEGAY (BLE) - 19/04/2016, 15:22:29 - v1.0.01
      - removed php dependencies (in url encode/decode and tab sorting)
     MODIFICATION : Bruno LEGAY (BLE) - 11/10/2016, 14:12:13 - v1.0.02
      - fixed comments in AWS_paramGet
     MODIFICATION : Bruno LEGAY (BLE) - 14/10/2016, 10:50:36 - v1.00.03
      - fixed templates "awsConfig-template.xml" and "awsCredentials-template.xml"
     MODIFICATION : Bruno LEGAY (BLE) - 18/10/2016, 07:31:03 - v1.00.04
      - fixed S3_restApi, signature pb when signing querystring like ""?uploads" (the implicit "=" was not added in the canonical querystring)
      - fixed S3_restApi,  content-type should be sent if not "" even when request body content is empty (useful for multipart uploads)
     MODIFICATION : Bruno LEGAY (BLE) - 03/01/2017, 20:36:53 - v1.00.05
      - added more log (dump xml error response) when aws replies with an error
     MODIFICATION : Bruno LEGAY (BLE) - 04/01/2017, 11:15:57 - v1.00.06
      - made JWT_test and HTTP_responseOk private methods
     MODIFICATION : Bruno LEGAY (BLE) - 04/04/2017, 22:00:01 - v1.00.07
      - added error handler around http request in S3_restApi
      - added logs to understand RequestTimeTooSkewed error
     MODIFICATION : Bruno LEGAY (BLE) - 04/04/2017, 22:00:01 - v1.00.08
      - added S3_easyBlobGet, S3_easyBlobPut, S3_easyFileGet, S3_easyFilePut
      MODIFICATION : Bruno LEGAY (BLE) - 01/07/2018, 08:48:40 - 1.00.09
      - added S3_fileUpload (with multipart)
      - in 4D v17+, native SHA256 will be used
      MODIFICATION : Bruno LEGAY (BLE) - 10/07/2018, 11:34:34 - 1.00.10
      - added AWS_credentialsCheck
     MODIFICATION : Bruno LEGAY (BLE) - 11/07/2018, 23:36:38 - 1.00.11
      - added AWS_configDirPathGet
      - fixed a bug in AWS_paramAuto (dir was not set properly)
     MODIFICATION : Bruno LEGAY (BLE) - 12/07/2018, 06:34:16 - 1.00.12
      - fixed logging OS X version
      - refactoring
     MODIFICATION : Bruno LEGAY (BLE) - 25/07/2018, 17:52:47 - 1.00.13
      - update region list
      - added S3_easyDelete
     MODIFICATION : Bruno LEGAY (BLE) - 25/07/2018, 19:01:02 - 1.00.14
      - fixed bug in AWS_credentialsCheck when $4 not used
    MODIFICATION : Bruno LEGAY (BLE) - 26/07/2018, 10:44:13 - 1.00.15
      - S3_bucketContentListGet made public (fix)  
    MODIFICATION : Bruno LEGAY (BLE) - 26/07/2018, 12:59:31 - 1.00.16
      - improved S3_bucketContentListRspParse (added nextContinuationTokenPtr parameter)
      - added S3_bucketContentListAllGet
    MODIFICATION : Bruno LEGAY (BLE) - 26/07/2018, 19:54:19 - 1.00.17
      - allow numeric array for size in S3_bucketContentListAllGet, S3_bucketContentListGet, S3_bucketContentListRspParse
      - added S3_bucketRegionGet
      - added AWS_paramRegionGet, AWS_paramRegionSet
    MODIFICATION : Bruno LEGAY (BLE) - 29/07/2018, 10:48:44 - 1.00.18
      - added more logs around credentials param setting and getting
    MODIFICATION : Bruno LEGAY (BLE) - 29/07/2018, 14:18:42 - 1.00.19
      - refactoring (added S3__styleApply and now using path style when there is a "." in the bucket name)
    MODIFICATION : Bruno LEGAY (BLE) - 30/07/2018, 10:19:45 - 1.00.20
      - S3_bucketContentListAllGet and S3_bucketContentListGet, $4 was mandatory
      - added AWS_debugFileShow
    MODIFICATION : Bruno LEGAY (BLE) - 30/07/2018, 19:00:57 - 1.00.21
      - improved "RequestTimeTooSkewed" error handling in AWS__requestErrorHdlr (when client time is +/- 15 mins desynchronized from aws servers time)

