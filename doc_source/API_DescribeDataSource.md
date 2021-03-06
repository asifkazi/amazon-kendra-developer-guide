--------

--------

# DescribeDataSource<a name="API_DescribeDataSource"></a>

Gets information about a Amazon Kendra data source\.

## Request Syntax<a name="API_DescribeDataSource_RequestSyntax"></a>

```
{
   "[Id](#Kendra-DescribeDataSource-request-Id)": "string",
   "[IndexId](#Kendra-DescribeDataSource-request-IndexId)": "string"
}
```

## Request Parameters<a name="API_DescribeDataSource_RequestParameters"></a>

For information about the parameters that are common to all actions, see [Common Parameters](CommonParameters.md)\.

The request accepts the following data in JSON format\.

 ** [Id](#API_DescribeDataSource_RequestSyntax) **   <a name="Kendra-DescribeDataSource-request-Id"></a>
The unique identifier of the data source to describe\.  
Type: String  
Length Constraints: Minimum length of 1\. Maximum length of 100\.  
Pattern: `[a-zA-Z0-9][a-zA-Z0-9_-]*`   
Required: Yes

 ** [IndexId](#API_DescribeDataSource_RequestSyntax) **   <a name="Kendra-DescribeDataSource-request-IndexId"></a>
The identifier of the index that contains the data source\.  
Type: String  
Length Constraints: Fixed length of 36\.  
Pattern: `[a-zA-Z0-9][a-zA-Z0-9-]*`   
Required: Yes

## Response Syntax<a name="API_DescribeDataSource_ResponseSyntax"></a>

```
{
   "[Configuration](#Kendra-DescribeDataSource-response-Configuration)": { 
      "[DatabaseConfiguration](API_DataSourceConfiguration.md#Kendra-Type-DataSourceConfiguration-DatabaseConfiguration)": { 
         "[AclConfiguration](API_DatabaseConfiguration.md#Kendra-Type-DatabaseConfiguration-AclConfiguration)": { 
            "[AllowedGroupsColumnName](API_AclConfiguration.md#Kendra-Type-AclConfiguration-AllowedGroupsColumnName)": "string"
         },
         "[ColumnConfiguration](API_DatabaseConfiguration.md#Kendra-Type-DatabaseConfiguration-ColumnConfiguration)": { 
            "[ChangeDetectingColumns](API_ColumnConfiguration.md#Kendra-Type-ColumnConfiguration-ChangeDetectingColumns)": [ "string" ],
            "[DocumentDataColumnName](API_ColumnConfiguration.md#Kendra-Type-ColumnConfiguration-DocumentDataColumnName)": "string",
            "[DocumentIdColumnName](API_ColumnConfiguration.md#Kendra-Type-ColumnConfiguration-DocumentIdColumnName)": "string",
            "[DocumentTitleColumnName](API_ColumnConfiguration.md#Kendra-Type-ColumnConfiguration-DocumentTitleColumnName)": "string",
            "[FieldMappings](API_ColumnConfiguration.md#Kendra-Type-ColumnConfiguration-FieldMappings)": [ 
               { 
                  "[DataSourceFieldName](API_DataSourceToIndexFieldMapping.md#Kendra-Type-DataSourceToIndexFieldMapping-DataSourceFieldName)": "string",
                  "[DateFieldFormat](API_DataSourceToIndexFieldMapping.md#Kendra-Type-DataSourceToIndexFieldMapping-DateFieldFormat)": "string",
                  "[IndexFieldName](API_DataSourceToIndexFieldMapping.md#Kendra-Type-DataSourceToIndexFieldMapping-IndexFieldName)": "string"
               }
            ]
         },
         "[ConnectionConfiguration](API_DatabaseConfiguration.md#Kendra-Type-DatabaseConfiguration-ConnectionConfiguration)": { 
            "[DatabaseHost](API_ConnectionConfiguration.md#Kendra-Type-ConnectionConfiguration-DatabaseHost)": "string",
            "[DatabaseName](API_ConnectionConfiguration.md#Kendra-Type-ConnectionConfiguration-DatabaseName)": "string",
            "[DatabasePort](API_ConnectionConfiguration.md#Kendra-Type-ConnectionConfiguration-DatabasePort)": number,
            "[SecretArn](API_ConnectionConfiguration.md#Kendra-Type-ConnectionConfiguration-SecretArn)": "string",
            "[TableName](API_ConnectionConfiguration.md#Kendra-Type-ConnectionConfiguration-TableName)": "string"
         },
         "[DatabaseEngineType](API_DatabaseConfiguration.md#Kendra-Type-DatabaseConfiguration-DatabaseEngineType)": "string",
         "[VpcConfiguration](API_DatabaseConfiguration.md#Kendra-Type-DatabaseConfiguration-VpcConfiguration)": { 
            "[SecurityGroupIds](API_DataSourceVpcConfiguration.md#Kendra-Type-DataSourceVpcConfiguration-SecurityGroupIds)": [ "string" ],
            "[SubnetIds](API_DataSourceVpcConfiguration.md#Kendra-Type-DataSourceVpcConfiguration-SubnetIds)": [ "string" ]
         }
      },
      "[OneDriveConfiguration](API_DataSourceConfiguration.md#Kendra-Type-DataSourceConfiguration-OneDriveConfiguration)": { 
         "[ExclusionPatterns](API_OneDriveConfiguration.md#Kendra-Type-OneDriveConfiguration-ExclusionPatterns)": [ "string" ],
         "[FieldMappings](API_OneDriveConfiguration.md#Kendra-Type-OneDriveConfiguration-FieldMappings)": [ 
            { 
               "[DataSourceFieldName](API_DataSourceToIndexFieldMapping.md#Kendra-Type-DataSourceToIndexFieldMapping-DataSourceFieldName)": "string",
               "[DateFieldFormat](API_DataSourceToIndexFieldMapping.md#Kendra-Type-DataSourceToIndexFieldMapping-DateFieldFormat)": "string",
               "[IndexFieldName](API_DataSourceToIndexFieldMapping.md#Kendra-Type-DataSourceToIndexFieldMapping-IndexFieldName)": "string"
            }
         ],
         "[InclusionPatterns](API_OneDriveConfiguration.md#Kendra-Type-OneDriveConfiguration-InclusionPatterns)": [ "string" ],
         "[OneDriveUsers](API_OneDriveConfiguration.md#Kendra-Type-OneDriveConfiguration-OneDriveUsers)": { 
            "[OneDriveUserList](API_OneDriveUsers.md#Kendra-Type-OneDriveUsers-OneDriveUserList)": [ "string" ],
            "[OneDriveUserS3Path](API_OneDriveUsers.md#Kendra-Type-OneDriveUsers-OneDriveUserS3Path)": { 
               "[Bucket](API_S3Path.md#Kendra-Type-S3Path-Bucket)": "string",
               "[Key](API_S3Path.md#Kendra-Type-S3Path-Key)": "string"
            }
         },
         "[SecretArn](API_OneDriveConfiguration.md#Kendra-Type-OneDriveConfiguration-SecretArn)": "string",
         "[TenantDomain](API_OneDriveConfiguration.md#Kendra-Type-OneDriveConfiguration-TenantDomain)": "string"
      },
      "[S3Configuration](API_DataSourceConfiguration.md#Kendra-Type-DataSourceConfiguration-S3Configuration)": { 
         "[AccessControlListConfiguration](API_S3DataSourceConfiguration.md#Kendra-Type-S3DataSourceConfiguration-AccessControlListConfiguration)": { 
            "[KeyPath](API_AccessControlListConfiguration.md#Kendra-Type-AccessControlListConfiguration-KeyPath)": "string"
         },
         "[BucketName](API_S3DataSourceConfiguration.md#Kendra-Type-S3DataSourceConfiguration-BucketName)": "string",
         "[DocumentsMetadataConfiguration](API_S3DataSourceConfiguration.md#Kendra-Type-S3DataSourceConfiguration-DocumentsMetadataConfiguration)": { 
            "[S3Prefix](API_DocumentsMetadataConfiguration.md#Kendra-Type-DocumentsMetadataConfiguration-S3Prefix)": "string"
         },
         "[ExclusionPatterns](API_S3DataSourceConfiguration.md#Kendra-Type-S3DataSourceConfiguration-ExclusionPatterns)": [ "string" ],
         "[InclusionPrefixes](API_S3DataSourceConfiguration.md#Kendra-Type-S3DataSourceConfiguration-InclusionPrefixes)": [ "string" ]
      },
      "[SalesforceConfiguration](API_DataSourceConfiguration.md#Kendra-Type-DataSourceConfiguration-SalesforceConfiguration)": { 
         "[ChatterFeedConfiguration](API_SalesforceConfiguration.md#Kendra-Type-SalesforceConfiguration-ChatterFeedConfiguration)": { 
            "[DocumentDataFieldName](API_SalesforceChatterFeedConfiguration.md#Kendra-Type-SalesforceChatterFeedConfiguration-DocumentDataFieldName)": "string",
            "[DocumentTitleFieldName](API_SalesforceChatterFeedConfiguration.md#Kendra-Type-SalesforceChatterFeedConfiguration-DocumentTitleFieldName)": "string",
            "[FieldMappings](API_SalesforceChatterFeedConfiguration.md#Kendra-Type-SalesforceChatterFeedConfiguration-FieldMappings)": [ 
               { 
                  "[DataSourceFieldName](API_DataSourceToIndexFieldMapping.md#Kendra-Type-DataSourceToIndexFieldMapping-DataSourceFieldName)": "string",
                  "[DateFieldFormat](API_DataSourceToIndexFieldMapping.md#Kendra-Type-DataSourceToIndexFieldMapping-DateFieldFormat)": "string",
                  "[IndexFieldName](API_DataSourceToIndexFieldMapping.md#Kendra-Type-DataSourceToIndexFieldMapping-IndexFieldName)": "string"
               }
            ],
            "[IncludeFilterTypes](API_SalesforceChatterFeedConfiguration.md#Kendra-Type-SalesforceChatterFeedConfiguration-IncludeFilterTypes)": [ "string" ]
         },
         "[CrawlAttachments](API_SalesforceConfiguration.md#Kendra-Type-SalesforceConfiguration-CrawlAttachments)": boolean,
         "[ExcludeAttachmentFilePatterns](API_SalesforceConfiguration.md#Kendra-Type-SalesforceConfiguration-ExcludeAttachmentFilePatterns)": [ "string" ],
         "[IncludeAttachmentFilePatterns](API_SalesforceConfiguration.md#Kendra-Type-SalesforceConfiguration-IncludeAttachmentFilePatterns)": [ "string" ],
         "[KnowledgeArticleConfiguration](API_SalesforceConfiguration.md#Kendra-Type-SalesforceConfiguration-KnowledgeArticleConfiguration)": { 
            "[CustomKnowledgeArticleTypeConfigurations](API_SalesforceKnowledgeArticleConfiguration.md#Kendra-Type-SalesforceKnowledgeArticleConfiguration-CustomKnowledgeArticleTypeConfigurations)": [ 
               { 
                  "[DocumentDataFieldName](API_SalesforceCustomKnowledgeArticleTypeConfiguration.md#Kendra-Type-SalesforceCustomKnowledgeArticleTypeConfiguration-DocumentDataFieldName)": "string",
                  "[DocumentTitleFieldName](API_SalesforceCustomKnowledgeArticleTypeConfiguration.md#Kendra-Type-SalesforceCustomKnowledgeArticleTypeConfiguration-DocumentTitleFieldName)": "string",
                  "[FieldMappings](API_SalesforceCustomKnowledgeArticleTypeConfiguration.md#Kendra-Type-SalesforceCustomKnowledgeArticleTypeConfiguration-FieldMappings)": [ 
                     { 
                        "[DataSourceFieldName](API_DataSourceToIndexFieldMapping.md#Kendra-Type-DataSourceToIndexFieldMapping-DataSourceFieldName)": "string",
                        "[DateFieldFormat](API_DataSourceToIndexFieldMapping.md#Kendra-Type-DataSourceToIndexFieldMapping-DateFieldFormat)": "string",
                        "[IndexFieldName](API_DataSourceToIndexFieldMapping.md#Kendra-Type-DataSourceToIndexFieldMapping-IndexFieldName)": "string"
                     }
                  ],
                  "[Name](API_SalesforceCustomKnowledgeArticleTypeConfiguration.md#Kendra-Type-SalesforceCustomKnowledgeArticleTypeConfiguration-Name)": "string"
               }
            ],
            "[IncludedStates](API_SalesforceKnowledgeArticleConfiguration.md#Kendra-Type-SalesforceKnowledgeArticleConfiguration-IncludedStates)": [ "string" ],
            "[StandardKnowledgeArticleTypeConfiguration](API_SalesforceKnowledgeArticleConfiguration.md#Kendra-Type-SalesforceKnowledgeArticleConfiguration-StandardKnowledgeArticleTypeConfiguration)": { 
               "[DocumentDataFieldName](API_SalesforceStandardKnowledgeArticleTypeConfiguration.md#Kendra-Type-SalesforceStandardKnowledgeArticleTypeConfiguration-DocumentDataFieldName)": "string",
               "[DocumentTitleFieldName](API_SalesforceStandardKnowledgeArticleTypeConfiguration.md#Kendra-Type-SalesforceStandardKnowledgeArticleTypeConfiguration-DocumentTitleFieldName)": "string",
               "[FieldMappings](API_SalesforceStandardKnowledgeArticleTypeConfiguration.md#Kendra-Type-SalesforceStandardKnowledgeArticleTypeConfiguration-FieldMappings)": [ 
                  { 
                     "[DataSourceFieldName](API_DataSourceToIndexFieldMapping.md#Kendra-Type-DataSourceToIndexFieldMapping-DataSourceFieldName)": "string",
                     "[DateFieldFormat](API_DataSourceToIndexFieldMapping.md#Kendra-Type-DataSourceToIndexFieldMapping-DateFieldFormat)": "string",
                     "[IndexFieldName](API_DataSourceToIndexFieldMapping.md#Kendra-Type-DataSourceToIndexFieldMapping-IndexFieldName)": "string"
                  }
               ]
            }
         },
         "[SecretArn](API_SalesforceConfiguration.md#Kendra-Type-SalesforceConfiguration-SecretArn)": "string",
         "[ServerUrl](API_SalesforceConfiguration.md#Kendra-Type-SalesforceConfiguration-ServerUrl)": "string",
         "[StandardObjectAttachmentConfiguration](API_SalesforceConfiguration.md#Kendra-Type-SalesforceConfiguration-StandardObjectAttachmentConfiguration)": { 
            "[DocumentTitleFieldName](API_SalesforceStandardObjectAttachmentConfiguration.md#Kendra-Type-SalesforceStandardObjectAttachmentConfiguration-DocumentTitleFieldName)": "string",
            "[FieldMappings](API_SalesforceStandardObjectAttachmentConfiguration.md#Kendra-Type-SalesforceStandardObjectAttachmentConfiguration-FieldMappings)": [ 
               { 
                  "[DataSourceFieldName](API_DataSourceToIndexFieldMapping.md#Kendra-Type-DataSourceToIndexFieldMapping-DataSourceFieldName)": "string",
                  "[DateFieldFormat](API_DataSourceToIndexFieldMapping.md#Kendra-Type-DataSourceToIndexFieldMapping-DateFieldFormat)": "string",
                  "[IndexFieldName](API_DataSourceToIndexFieldMapping.md#Kendra-Type-DataSourceToIndexFieldMapping-IndexFieldName)": "string"
               }
            ]
         },
         "[StandardObjectConfigurations](API_SalesforceConfiguration.md#Kendra-Type-SalesforceConfiguration-StandardObjectConfigurations)": [ 
            { 
               "[DocumentDataFieldName](API_SalesforceStandardObjectConfiguration.md#Kendra-Type-SalesforceStandardObjectConfiguration-DocumentDataFieldName)": "string",
               "[DocumentTitleFieldName](API_SalesforceStandardObjectConfiguration.md#Kendra-Type-SalesforceStandardObjectConfiguration-DocumentTitleFieldName)": "string",
               "[FieldMappings](API_SalesforceStandardObjectConfiguration.md#Kendra-Type-SalesforceStandardObjectConfiguration-FieldMappings)": [ 
                  { 
                     "[DataSourceFieldName](API_DataSourceToIndexFieldMapping.md#Kendra-Type-DataSourceToIndexFieldMapping-DataSourceFieldName)": "string",
                     "[DateFieldFormat](API_DataSourceToIndexFieldMapping.md#Kendra-Type-DataSourceToIndexFieldMapping-DateFieldFormat)": "string",
                     "[IndexFieldName](API_DataSourceToIndexFieldMapping.md#Kendra-Type-DataSourceToIndexFieldMapping-IndexFieldName)": "string"
                  }
               ],
               "[Name](API_SalesforceStandardObjectConfiguration.md#Kendra-Type-SalesforceStandardObjectConfiguration-Name)": "string"
            }
         ]
      },
      "[ServiceNowConfiguration](API_DataSourceConfiguration.md#Kendra-Type-DataSourceConfiguration-ServiceNowConfiguration)": { 
         "[HostUrl](API_ServiceNowConfiguration.md#Kendra-Type-ServiceNowConfiguration-HostUrl)": "string",
         "[KnowledgeArticleConfiguration](API_ServiceNowConfiguration.md#Kendra-Type-ServiceNowConfiguration-KnowledgeArticleConfiguration)": { 
            "[CrawlAttachments](API_ServiceNowKnowledgeArticleConfiguration.md#Kendra-Type-ServiceNowKnowledgeArticleConfiguration-CrawlAttachments)": boolean,
            "[DocumentDataFieldName](API_ServiceNowKnowledgeArticleConfiguration.md#Kendra-Type-ServiceNowKnowledgeArticleConfiguration-DocumentDataFieldName)": "string",
            "[DocumentTitleFieldName](API_ServiceNowKnowledgeArticleConfiguration.md#Kendra-Type-ServiceNowKnowledgeArticleConfiguration-DocumentTitleFieldName)": "string",
            "[ExcludeAttachmentFilePatterns](API_ServiceNowKnowledgeArticleConfiguration.md#Kendra-Type-ServiceNowKnowledgeArticleConfiguration-ExcludeAttachmentFilePatterns)": [ "string" ],
            "[FieldMappings](API_ServiceNowKnowledgeArticleConfiguration.md#Kendra-Type-ServiceNowKnowledgeArticleConfiguration-FieldMappings)": [ 
               { 
                  "[DataSourceFieldName](API_DataSourceToIndexFieldMapping.md#Kendra-Type-DataSourceToIndexFieldMapping-DataSourceFieldName)": "string",
                  "[DateFieldFormat](API_DataSourceToIndexFieldMapping.md#Kendra-Type-DataSourceToIndexFieldMapping-DateFieldFormat)": "string",
                  "[IndexFieldName](API_DataSourceToIndexFieldMapping.md#Kendra-Type-DataSourceToIndexFieldMapping-IndexFieldName)": "string"
               }
            ],
            "[IncludeAttachmentFilePatterns](API_ServiceNowKnowledgeArticleConfiguration.md#Kendra-Type-ServiceNowKnowledgeArticleConfiguration-IncludeAttachmentFilePatterns)": [ "string" ]
         },
         "[SecretArn](API_ServiceNowConfiguration.md#Kendra-Type-ServiceNowConfiguration-SecretArn)": "string",
         "[ServiceCatalogConfiguration](API_ServiceNowConfiguration.md#Kendra-Type-ServiceNowConfiguration-ServiceCatalogConfiguration)": { 
            "[CrawlAttachments](API_ServiceNowServiceCatalogConfiguration.md#Kendra-Type-ServiceNowServiceCatalogConfiguration-CrawlAttachments)": boolean,
            "[DocumentDataFieldName](API_ServiceNowServiceCatalogConfiguration.md#Kendra-Type-ServiceNowServiceCatalogConfiguration-DocumentDataFieldName)": "string",
            "[DocumentTitleFieldName](API_ServiceNowServiceCatalogConfiguration.md#Kendra-Type-ServiceNowServiceCatalogConfiguration-DocumentTitleFieldName)": "string",
            "[ExcludeAttachmentFilePatterns](API_ServiceNowServiceCatalogConfiguration.md#Kendra-Type-ServiceNowServiceCatalogConfiguration-ExcludeAttachmentFilePatterns)": [ "string" ],
            "[FieldMappings](API_ServiceNowServiceCatalogConfiguration.md#Kendra-Type-ServiceNowServiceCatalogConfiguration-FieldMappings)": [ 
               { 
                  "[DataSourceFieldName](API_DataSourceToIndexFieldMapping.md#Kendra-Type-DataSourceToIndexFieldMapping-DataSourceFieldName)": "string",
                  "[DateFieldFormat](API_DataSourceToIndexFieldMapping.md#Kendra-Type-DataSourceToIndexFieldMapping-DateFieldFormat)": "string",
                  "[IndexFieldName](API_DataSourceToIndexFieldMapping.md#Kendra-Type-DataSourceToIndexFieldMapping-IndexFieldName)": "string"
               }
            ],
            "[IncludeAttachmentFilePatterns](API_ServiceNowServiceCatalogConfiguration.md#Kendra-Type-ServiceNowServiceCatalogConfiguration-IncludeAttachmentFilePatterns)": [ "string" ]
         },
         "[ServiceNowBuildVersion](API_ServiceNowConfiguration.md#Kendra-Type-ServiceNowConfiguration-ServiceNowBuildVersion)": "string"
      },
      "[SharePointConfiguration](API_DataSourceConfiguration.md#Kendra-Type-DataSourceConfiguration-SharePointConfiguration)": { 
         "[CrawlAttachments](API_SharePointConfiguration.md#Kendra-Type-SharePointConfiguration-CrawlAttachments)": boolean,
         "[DocumentTitleFieldName](API_SharePointConfiguration.md#Kendra-Type-SharePointConfiguration-DocumentTitleFieldName)": "string",
         "[ExclusionPatterns](API_SharePointConfiguration.md#Kendra-Type-SharePointConfiguration-ExclusionPatterns)": [ "string" ],
         "[FieldMappings](API_SharePointConfiguration.md#Kendra-Type-SharePointConfiguration-FieldMappings)": [ 
            { 
               "[DataSourceFieldName](API_DataSourceToIndexFieldMapping.md#Kendra-Type-DataSourceToIndexFieldMapping-DataSourceFieldName)": "string",
               "[DateFieldFormat](API_DataSourceToIndexFieldMapping.md#Kendra-Type-DataSourceToIndexFieldMapping-DateFieldFormat)": "string",
               "[IndexFieldName](API_DataSourceToIndexFieldMapping.md#Kendra-Type-DataSourceToIndexFieldMapping-IndexFieldName)": "string"
            }
         ],
         "[InclusionPatterns](API_SharePointConfiguration.md#Kendra-Type-SharePointConfiguration-InclusionPatterns)": [ "string" ],
         "[SecretArn](API_SharePointConfiguration.md#Kendra-Type-SharePointConfiguration-SecretArn)": "string",
         "[SharePointVersion](API_SharePointConfiguration.md#Kendra-Type-SharePointConfiguration-SharePointVersion)": "string",
         "[Urls](API_SharePointConfiguration.md#Kendra-Type-SharePointConfiguration-Urls)": [ "string" ],
         "[UseChangeLog](API_SharePointConfiguration.md#Kendra-Type-SharePointConfiguration-UseChangeLog)": boolean,
         "[VpcConfiguration](API_SharePointConfiguration.md#Kendra-Type-SharePointConfiguration-VpcConfiguration)": { 
            "[SecurityGroupIds](API_DataSourceVpcConfiguration.md#Kendra-Type-DataSourceVpcConfiguration-SecurityGroupIds)": [ "string" ],
            "[SubnetIds](API_DataSourceVpcConfiguration.md#Kendra-Type-DataSourceVpcConfiguration-SubnetIds)": [ "string" ]
         }
      }
   },
   "[CreatedAt](#Kendra-DescribeDataSource-response-CreatedAt)": number,
   "[Description](#Kendra-DescribeDataSource-response-Description)": "string",
   "[ErrorMessage](#Kendra-DescribeDataSource-response-ErrorMessage)": "string",
   "[Id](#Kendra-DescribeDataSource-response-Id)": "string",
   "[IndexId](#Kendra-DescribeDataSource-response-IndexId)": "string",
   "[Name](#Kendra-DescribeDataSource-response-Name)": "string",
   "[RoleArn](#Kendra-DescribeDataSource-response-RoleArn)": "string",
   "[Schedule](#Kendra-DescribeDataSource-response-Schedule)": "string",
   "[Status](#Kendra-DescribeDataSource-response-Status)": "string",
   "[Type](#Kendra-DescribeDataSource-response-Type)": "string",
   "[UpdatedAt](#Kendra-DescribeDataSource-response-UpdatedAt)": number
}
```

## Response Elements<a name="API_DescribeDataSource_ResponseElements"></a>

If the action is successful, the service sends back an HTTP 200 response\.

The following data is returned in JSON format by the service\.

 ** [Configuration](#API_DescribeDataSource_ResponseSyntax) **   <a name="Kendra-DescribeDataSource-response-Configuration"></a>
Information that describes where the data source is located and how the data source is configured\. The specific information in the description depends on the data source provider\.  
Type: [DataSourceConfiguration](API_DataSourceConfiguration.md) object

 ** [CreatedAt](#API_DescribeDataSource_ResponseSyntax) **   <a name="Kendra-DescribeDataSource-response-CreatedAt"></a>
The Unix timestamp of when the data source was created\.  
Type: Timestamp

 ** [Description](#API_DescribeDataSource_ResponseSyntax) **   <a name="Kendra-DescribeDataSource-response-Description"></a>
The description of the data source\.  
Type: String  
Length Constraints: Minimum length of 1\. Maximum length of 1000\.  
Pattern: `^\P{C}*$` 

 ** [ErrorMessage](#API_DescribeDataSource_ResponseSyntax) **   <a name="Kendra-DescribeDataSource-response-ErrorMessage"></a>
When the `Status` field value is `FAILED`, the `ErrorMessage` field contains a description of the error that caused the data source to fail\.  
Type: String  
Length Constraints: Minimum length of 1\. Maximum length of 2048\.  
Pattern: `^\P{C}*$` 

 ** [Id](#API_DescribeDataSource_ResponseSyntax) **   <a name="Kendra-DescribeDataSource-response-Id"></a>
The identifier of the data source\.  
Type: String  
Length Constraints: Minimum length of 1\. Maximum length of 100\.  
Pattern: `[a-zA-Z0-9][a-zA-Z0-9_-]*` 

 ** [IndexId](#API_DescribeDataSource_ResponseSyntax) **   <a name="Kendra-DescribeDataSource-response-IndexId"></a>
The identifier of the index that contains the data source\.  
Type: String  
Length Constraints: Fixed length of 36\.  
Pattern: `[a-zA-Z0-9][a-zA-Z0-9-]*` 

 ** [Name](#API_DescribeDataSource_ResponseSyntax) **   <a name="Kendra-DescribeDataSource-response-Name"></a>
The name that you gave the data source when it was created\.  
Type: String  
Length Constraints: Minimum length of 1\. Maximum length of 1000\.  
Pattern: `[a-zA-Z0-9][a-zA-Z0-9_-]*` 

 ** [RoleArn](#API_DescribeDataSource_ResponseSyntax) **   <a name="Kendra-DescribeDataSource-response-RoleArn"></a>
The Amazon Resource Name \(ARN\) of the role that enables the data source to access its resources\.  
Type: String  
Length Constraints: Minimum length of 1\. Maximum length of 1284\.  
Pattern: `arn:[a-z0-9-\.]{1,63}:[a-z0-9-\.]{0,63}:[a-z0-9-\.]{0,63}:[a-z0-9-\.]{0,63}:[^/].{0,1023}` 

 ** [Schedule](#API_DescribeDataSource_ResponseSyntax) **   <a name="Kendra-DescribeDataSource-response-Schedule"></a>
The schedule that Amazon Kendra will update the data source\.  
Type: String

 ** [Status](#API_DescribeDataSource_ResponseSyntax) **   <a name="Kendra-DescribeDataSource-response-Status"></a>
The current status of the data source\. When the status is `ACTIVE` the data source is ready to use\. When the status is `FAILED`, the `ErrorMessage` field contains the reason that the data source failed\.  
Type: String  
Valid Values:` CREATING | DELETING | FAILED | UPDATING | ACTIVE` 

 ** [Type](#API_DescribeDataSource_ResponseSyntax) **   <a name="Kendra-DescribeDataSource-response-Type"></a>
The type of the data source\.  
Type: String  
Valid Values:` S3 | SHAREPOINT | DATABASE | SALESFORCE | ONEDRIVE | SERVICENOW` 

 ** [UpdatedAt](#API_DescribeDataSource_ResponseSyntax) **   <a name="Kendra-DescribeDataSource-response-UpdatedAt"></a>
The Unix timestamp of when the data source was last updated\.  
Type: Timestamp

## Errors<a name="API_DescribeDataSource_Errors"></a>

For information about the errors that are common to all actions, see [Common Errors](CommonErrors.md)\.

 **AccessDeniedException**   
HTTP Status Code: 400

 **InternalServerException**   
HTTP Status Code: 500

 **ResourceNotFoundException**   
HTTP Status Code: 400

 **ThrottlingException**   
HTTP Status Code: 400

 **ValidationException**   
HTTP Status Code: 400

## See Also<a name="API_DescribeDataSource_SeeAlso"></a>

For more information about using this API in one of the language\-specific AWS SDKs, see the following:
+  [AWS Command Line Interface](https://docs.aws.amazon.com/goto/aws-cli/kendra-2019-02-03/DescribeDataSource) 
+  [AWS SDK for \.NET](https://docs.aws.amazon.com/goto/DotNetSDKV3/kendra-2019-02-03/DescribeDataSource) 
+  [AWS SDK for C\+\+](https://docs.aws.amazon.com/goto/SdkForCpp/kendra-2019-02-03/DescribeDataSource) 
+  [AWS SDK for Go](https://docs.aws.amazon.com/goto/SdkForGoV1/kendra-2019-02-03/DescribeDataSource) 
+  [AWS SDK for Java](https://docs.aws.amazon.com/goto/SdkForJava/kendra-2019-02-03/DescribeDataSource) 
+  [AWS SDK for JavaScript](https://docs.aws.amazon.com/goto/AWSJavaScriptSDK/kendra-2019-02-03/DescribeDataSource) 
+  [AWS SDK for PHP V3](https://docs.aws.amazon.com/goto/SdkForPHPV3/kendra-2019-02-03/DescribeDataSource) 
+  [AWS SDK for Python](https://docs.aws.amazon.com/goto/boto3/kendra-2019-02-03/DescribeDataSource) 
+  [AWS SDK for Ruby V3](https://docs.aws.amazon.com/goto/SdkForRubyV3/kendra-2019-02-03/DescribeDataSource) 