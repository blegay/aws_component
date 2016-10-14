# aws_component
# This 4D component enable to interact with AWS and more specifically S3.
# The component has been written in 4D v14.
# The demo is written in 4D v15.x
# 
# https://www.linkedin.com/in/brunolegay
#
# 
#      CREATION : Bruno LEGAY (BLE) - 03/01/2016, 13:53:50 - v0.9.00
#      MODIFICATION : Bruno LEGAY (BLE) - 25/02/2016, 10:25:01 - v0.9.03
#       - added AWS__endpointGet, AWS__serviceList AWS__serviceRegionList
#       - and updated AWS_restApi and AWS_authQueryUrl
#      MODIFICATION : Bruno LEGAY (BLE) - 03/03/2016, 20:22:56 - v0.9.04
#       - allow empty request body or nil for AWS_restApi (#Keith)
#      MODIFICATION : Bruno LEGAY (BLE) - 02/03/2016, 18:45:12 - v0.9.05
#       - added query string sort for canonical request (AWS__canonicalQueryStrSort)
#      MODIFICATION : Bruno LEGAY (BLE) - 17/04/2016, 19:18:23 - v1.0.00
#       - renames AWS_restApi into S3_restApi and removed "$1" parameter
#       - fixed bugs in sorting query parameters and headers (4D sort is case sensitive, AWS is not case sensitive). See TAB_sortArrayCaseSensitive, TAB_sortArrayMultiCaseSensitive (php, 4D v14-json)
#       - fixed potential bugs in uri encoding (improved compliance to AWS specs). see S3_uriEncode
#       - refactoring
#       - AWS_testCases
#       - fixed a bug in S3_restApi when using empty "Content-Type"
#      MODIFICATION : Bruno LEGAY (BLE) - 19/04/2016, 15:22:29 - v1.0.01
#       - removed php dependencies (in url encode/decode and tab sorting)
#      MODIFICATION : Bruno LEGAY (BLE) - 11/10/2016, 14:12:13 - v1.0.02
#       - fixed comments in AWS_paramGet
#      MODIFICATION : Bruno LEGAY (BLE) - 14/10/2016, 10:50:36 - v1.00.03
#       - fixed templates "awsConfig-template.xml" and "awsCredentials-template.xml"