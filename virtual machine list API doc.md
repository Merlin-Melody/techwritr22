# virtual Machines - Lists #


Lists all of the virtual machines in the specified resource group. Use the nextLink property in the response to get the next page of virtual machines.

```

GET https://management.azure.com/subscriptions/{subscriptionId}/resourceGroups/{resourceGroupName}/providers/Microsoft.Compute/virtualMachines?api-version=2022-08-01

```

With optional parameters

```

GET https://management.azure.com/subscriptions/{subscriptionId}/resourceGroups/{resourceGroupName}/providers/Microsoft.Compute/virtualMachines?$filter={$filter}&api-version=2022-08-01

```

**URI Parameters**



| Name               | In    | Required | Type   | Description                                                                                                                                                                                                                                  |
|--------------------|-------|----------|--------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| `resource Groupname` | path  | True     | string | The name of the resource group                                                                                                                                                                                                               |
| `Subscription Id`  | path  | True     | string | Subscription credentials which uniquely identify Microsoft Azure subscription. The subscription ID forms part of the URI for every service call.                                                                                             |
| `API version`      | query | True     | string | Client Api Version.                                                                                                                                                                                                                          |
| `$Filter`           | query |          | string | The system query option to filter VMs returned in the response. Allowed value is 'virtualMachineScaleSet/id' eq /subscriptions/{subId}/resourceGroups/{resourceGroupName}/providers/Microsoft.Compute/virtualMachineScaleSets/{vmssName}' \| |

## Responses ##



| Name              | Type                        | Description                                        |
|-------------------|-----------------------------|----------------------------------------------------|
| 200 OK            | Virtual machine List result | OK                                                 |
| other status code | cloud error                 | Error response describing why the operation failed |



# Security #

## azure_auth
Azure Active Directory OAuth2 Flow



Type: oauth2

Flow: implicit

Authorization URL: https://login.microsoftonline.com/common/oauth2/authorize



## Scopes ##
| Name               | Description                   |
|--------------------|-------------------------------|
| user_impersonation | impersonate your user account |

## Example ##

### VirtualMachines_List_MaximumSet_Gen ###

### sample request ###

`GET https://management.azure.com/subscriptions/{subscription-id}/resourceGroups/rgcompute/providers/Microsoft.Compute/virtualMachines?$filter=aaaaaaaaaaaaaaaaaaaaaaa&api-version=2022-08-01`

### Sample response ###

status code 200

```json

{

  "value": [

    {

      "properties": {

        "vmId": "{vmId}",

        "availabilitySet": {

          "id": "/subscriptions/{subscriptionId}/resourceGroups/{resourceGroupName}/providers/Microsoft.Compute/availabilitySets/{availabilitySetName}"

        },

        "hardwareProfile": {

          "vmSize": "Standard_A0",

          "vmSizeProperties": {

            "vCPUsAvailable": 7,

            "vCPUsPerCore": 14

          }

        },

        "storageProfile": {

          "imageReference": {

            "publisher": "MicrosoftWindowsServer",

            "offer": "WindowsServer",

            "sku": "2012-R2-Datacenter",

            "version": "4.127.20170406",

            "exactVersion": "aaaaaaaaaaaaa",

            "sharedGalleryImageId": "aaaaaaaaaaaaaaa",

            "communityGalleryImageId": "aaaa",

            "id": "aaaaaaaaaaaaaaaaaaaaaaaaaaaaaa"

          },

          "osDisk": {

            "osType": "Windows",

            "name": "test",

            "createOption": "FromImage",

            "vhd": {

              "uri": "https://{storageAccountName}.blob.core.windows.net/{containerName}/{vhdName}.vhd"

            },

            "caching": "None",

            "diskSizeGB": 127,

            "encryptionSettings": {

              "diskEncryptionKey": {

                "secretUrl": "aaaaaaaaa",

                "sourceVault": {

                  "id": "/subscriptions/{subscriptionId}/resourceGroups/{resourceGroupName}/providers/Microsoft.Compute/availabilitySets/{availabilitySetName}"

                }

              },

              "keyEncryptionKey": {

                "keyUrl": "aaaaaaaaaaaaa",

                "sourceVault": {

                  "id": "/subscriptions/{subscriptionId}/resourceGroups/{resourceGroupName}/providers/Microsoft.Compute/availabilitySets/{availabilitySetName}"

                }

              },

              "enabled": true

            },

            "image": {

              "uri": "https://{storageAccountName}.blob.core.windows.net/{containerName}/{vhdName}.vhd"

            },

            "writeAcceleratorEnabled": true,

            "diffDiskSettings": {

              "option": "Local",

              "placement": "CacheDisk"

            },

            "managedDisk": {

              "storageAccountType": "Standard_LRS",

              "diskEncryptionSet": {

                "id": "aaaaaaaaaaaaaaaaaaaaaaaaaaaa"

              },

              "securityProfile": {

                "securityEncryptionType": "VMGuestStateOnly",

                "diskEncryptionSet": {

                  "id": "aaaaaaaaaaaaaaaaaaaaaaaaaaaa"

                }

              },

              "id": "/subscriptions/{subscription-id}/resourceGroups/myResourceGroup/providers/Microsoft.Compute/disks/testingexcludedisk_OsDisk_1_74cdaedcea50483d9833c96adefa100f"

            },

            "deleteOption": "Delete"

          },

          "dataDisks": []

        },

        "osProfile": {

          "computerName": "Test",

          "adminUsername": "Foo12",

          "windowsConfiguration": {

            "provisionVMAgent": true,

            "enableAutomaticUpdates": true,

            "timeZone": "aaaaaaaaaaaaaaaaaaaaaa",

            "additionalUnattendContent": [

              {

                "passName": "OobeSystem",

                "componentName": "Microsoft-Windows-Shell-Setup",

                "settingName": "AutoLogon",

                "content": "aaaaaaaaaaaaaaaaaaaaaaaaaa"

              }

            ],

            "patchSettings": {

              "patchMode": "Manual",

              "enableHotpatching": true,

              "assessmentMode": "ImageDefault"

            },

            "winRM": {

              "listeners": [

                {

                  "protocol": "Http",

                  "certificateUrl": "aaaaaaaaaaaaaaaaaaaaa"

                }

              ]

            }

          },

          "secrets": [],

          "allowExtensionOperations": true,

          "customData": "aaaa",

          "linuxConfiguration": {

            "disablePasswordAuthentication": true,

            "ssh": {

              "publicKeys": [

                {

                  "path": "aaaaaaaaaaaaaaaaaaaaaa",

                  "keyData": "aaa"

                }

              ]

            },

            "provisionVMAgent": true,

            "patchSettings": {

              "patchMode": "ImageDefault",

              "assessmentMode": "ImageDefault"

            }

          },

          "requireGuestProvisionSignal": true

        },

        "networkProfile": {

          "networkInterfaces": [

            {

              "id": "/subscriptions/{subscriptionId}/resourceGroups/{resourceGroupName}/providers/Microsoft.Network/networkInterfaces/{networkInterfaceName}",

              "properties": {

                "primary": true,

                "deleteOption": "Delete"

              }

            }

          ],

          "networkApiVersion": "2022-05-01",

          "networkInterfaceConfigurations": [

            {

              "name": "aaaaaaaa",

              "properties": {

                "primary": true,

                "deleteOption": "Delete",

                "enableAcceleratedNetworking": true,

                "disableTcpStateTracking": true,

                "enableFpga": true,

                "enableIPForwarding": true,

                "networkSecurityGroup": {

                  "id": "/subscriptions/{subscriptionId}/resourceGroups/{resourceGroupName}/providers/Microsoft.Compute/availabilitySets/{availabilitySetName}"

                },

                "dnsSettings": {

                  "dnsServers": [

                    "aaaaaaaaaaaaaaaaaaaaaaaa"

                  ]

                },

                "ipConfigurations": [

                  {

                    "name": "aaaaaaaa",

                    "properties": {

                      "subnet": {

                        "id": "/subscriptions/{subscriptionId}/resourceGroups/{resourceGroupName}/providers/Microsoft.Compute/availabilitySets/{availabilitySetName}"

                      },

                      "primary": true,

                      "publicIPAddressConfiguration": {

                        "name": "aaaaaaaaaaaaaaaaaa",

                        "properties": {

                          "idleTimeoutInMinutes": 23,

                          "deleteOption": "Delete",

                          "dnsSettings": {

                            "domainNameLabel": "aaaaa"

                          },

                          "ipTags": [

                            {

                              "ipTagType": "aaaaa",

                              "tag": "aaaaaaaaaaaaaaaaaaaaaaaaaaa"

                            }

                          ],

                          "publicIPPrefix": {

                            "id": "/subscriptions/{subscriptionId}/resourceGroups/{resourceGroupName}/providers/Microsoft.Compute/availabilitySets/{availabilitySetName}"

                          },

                          "publicIPAddressVersion": "IPv4",

                          "publicIPAllocationMethod": "Dynamic"

                        },

                        "sku": {

                          "name": "Basic",

                          "tier": "Regional"

                        }

                      },

                      "privateIPAddressVersion": "IPv4",

                      "applicationSecurityGroups": [

                        {

                          "id": "/subscriptions/{subscriptionId}/resourceGroups/{resourceGroupName}/providers/Microsoft.Compute/availabilitySets/{availabilitySetName}"

                        }

                      ],

                      "applicationGatewayBackendAddressPools": [

                        {

                          "id": "/subscriptions/{subscriptionId}/resourceGroups/{resourceGroupName}/providers/Microsoft.Compute/availabilitySets/{availabilitySetName}"

                        }

                      ],

                      "loadBalancerBackendAddressPools": [

                        {

                          "id": "/subscriptions/{subscriptionId}/resourceGroups/{resourceGroupName}/providers/Microsoft.Compute/availabilitySets/{availabilitySetName}"

                        }

                      ]

                    }

                  }

                ],

                "dscpConfiguration": {

                  "id": "/subscriptions/{subscriptionId}/resourceGroups/{resourceGroupName}/providers/Microsoft.Compute/availabilitySets/{availabilitySetName}"

                }

              }

            }

          ]

        },

        "provisioningState": "Succeeded",

        "additionalCapabilities": {

          "ultraSSDEnabled": true,

          "hibernationEnabled": true

        },

        "securityProfile": {

          "uefiSettings": {

            "secureBootEnabled": true,

            "vTpmEnabled": true

          },

          "encryptionAtHost": true,

          "securityType": "TrustedLaunch"

        },

        "diagnosticsProfile": {

          "bootDiagnostics": {

            "enabled": true,

            "storageUri": "aaaaaaaaaaaaaaaaaaaaa"

          }

        },

        "virtualMachineScaleSet": {

          "id": "/subscriptions/{subscriptionId}/resourceGroups/{resourceGroupName}/providers/Microsoft.Compute/availabilitySets/{availabilitySetName}"

        },

        "proximityPlacementGroup": {

          "id": "/subscriptions/{subscriptionId}/resourceGroups/{resourceGroupName}/providers/Microsoft.Compute/availabilitySets/{availabilitySetName}"

        },

        "priority": "Regular",

        "evictionPolicy": "Deallocate",

        "billingProfile": {

          "maxPrice": 26

        },

        "host": {

          "id": "/subscriptions/{subscriptionId}/resourceGroups/{resourceGroupName}/providers/Microsoft.Compute/availabilitySets/{availabilitySetName}"

        },

        "hostGroup": {

          "id": "/subscriptions/{subscriptionId}/resourceGroups/{resourceGroupName}/providers/Microsoft.Compute/availabilitySets/{availabilitySetName}"

        },

        "licenseType": "aaaaaaaaaaaaaaa",

        "extensionsTimeBudget": "aaaaaaaaaaaaaaaaaaaaaaaaaaaa",

        "platformFaultDomain": 8,

        "scheduledEventsProfile": {

          "terminateNotificationProfile": {

            "notBeforeTimeout": "aaaaaaaaaaaaaaaaaaaaaaaaaaaa",

            "enable": true

          }

        },

        "userData": "aaa",

        "capacityReservation": {

          "capacityReservationGroup": {

            "id": "/subscriptions/{subscriptionId}/resourceGroups/{resourceGroupName}/providers/Microsoft.Compute/availabilitySets/{availabilitySetName}"

          }

        },

        "applicationProfile": {

          "galleryApplications": [

            {

              "tags": "aaaaa",

              "order": 4,

              "packageReferenceId": "aaaaaaaaaaaaaaaaaaaaaa",

              "configurationReference": "aaaaaaaaaaaaaaaaaaaaaaaaaaaaaa"

            }

          ]

        },

        "timeCreated": "2022-01-14T16:43:41.683Z"

      },

      "type": "Microsoft.Compute/virtualMachines",

      "location": "eastus",

      "tags": {},

      "id": "/subscriptions/{subscriptionId}/resourceGroups/{resourceGroupName}/providers/Microsoft.Compute/virtualMachines/{virtualMachineName}",

      "name": "{virtualMachineName}",

      "plan": {

        "name": "aaaaaaaaaaaaaaaaaa",

        "publisher": "aaaaaaaaaaaaaaaaa",

        "product": "aaaaaaaaaaaaaaaaaaaaaa",

        "promotionCode": "aaaaaaaaaaaaaa"

      },

      "resources": [

        {

          "properties": {

            "forceUpdateTag": "aaaaaaaaaaaaaaa",

            "publisher": "aaaaaaaaaaaaaaaa",

            "type": "aaaaaaaa",

            "typeHandlerVersion": "aaaaaaaaaaaa",

            "autoUpgradeMinorVersion": true,

            "enableAutomaticUpgrade": true,

            "settings": {},

            "protectedSettings": {},

            "provisioningState": "aaa",

            "instanceView": {

              "name": "aaaaaaaaaaaaaaaaaaaaaaaa",

              "type": "aaaaaaaaaaaaaaaaaaaaaaaa",

              "typeHandlerVersion": "aaaaaa",

              "substatuses": [

                {

                  "code": "aaa",

                  "level": "Info",

                  "displayStatus": "aaaaaaaaaaaaaaaaaaaaaaaa",

                  "message": "aaaaaaaaaaaaaaaaaaa",

                  "time": "2022-01-14T16:43:41.657Z"

                }

              ],

              "statuses": [

                {

                  "code": "aaa",

                  "level": "Info",

                  "displayStatus": "aaaaaaaaaaaaaaaaaaaaaaaa",

                  "message": "aaaaaaaaaaaaaaaaaaa",

                  "time": "2022-01-14T16:43:41.657Z"

                }

              ]

            },

            "suppressFailures": true,

            "protectedSettingsFromKeyVault": {

              "sourceVault": {

                "id": "/subscriptions/a53f7094-a16c-47af-abe4-b05c05d0d79a/resourceGroups/myResourceGroup/providers/Microsoft.KeyVault/vaults/kvName"

              },

              "secretUrl": "https://kvName.vault.azure.net/secrets/secretName/79b88b3a6f5440ffb2e73e44a0db712e"

            }

          },

          "id": "aaaaaaaaaaaaaaaaaaaaaaaaaaaaa",

          "name": "aaaaaaaaaaaaa",

          "type": "aaaaaaaaaaaaaaaaaaaaaaaaaaa",

          "location": "aaaaaaaaaaaaaaaa",

          "tags": {

            "key9428": "aaaaaaa"

          }

        }

      ],

      "identity": {

        "principalId": "aaaaaaaaaaaaaaaa",

        "tenantId": "aaaaa",

        "type": "SystemAssigned",

        "userAssignedIdentities": {

          "key5688": {

            "principalId": "aaaaaaaaaaaaaaa",

            "clientId": "aaaaaaaaaaa"

          }

        }

      },

      "zones": [

        "aaaaaaaaaaaaaaaaaaaaaaaaaaa"

      ],

      "extendedLocation": {

        "name": "aaaa",

        "type": "EdgeZone"

      }

    },

    {

      "properties": {

        "vmId": "{vmId}",

        "availabilitySet": {

          "id": "/subscriptions/{subscriptionId}/resourceGroups/{resourceGroupName}/providers/Microsoft.Compute/availabilitySets/{availabilitySetName}"

        },

        "hardwareProfile": {

          "vmSize": "Standard_A0",

          "vmSizeProperties": {

            "vCPUsAvailable": 7,

            "vCPUsPerCore": 14

          }

        },

        "storageProfile": {

          "imageReference": {

            "publisher": "MicrosoftWindowsServer",

            "offer": "WindowsServer",

            "sku": "2012-R2-Datacenter",

            "version": "4.127.20170406",

            "exactVersion": "aa",

            "sharedGalleryImageId": "aaaaaaaaaaaaaaaaaaaaaaaaa",

            "communityGalleryImageId": "aaaaaaaaaaaaaaaaaaaaaaaaaaaa",

            "id": "aaaaaaaa"

          },

          "osDisk": {

            "osType": "Windows",

            "name": "test",

            "createOption": "FromImage",

            "vhd": {

              "uri": "https://{storageAccountName}.blob.core.windows.net/{containerName}/{vhdName}.vhd"

            },

            "caching": "None",

            "diskSizeGB": 127,

            "encryptionSettings": {

              "diskEncryptionKey": {

                "secretUrl": "aaaaaaaaa",

                "sourceVault": {

                  "id": "/subscriptions/{subscriptionId}/resourceGroups/{resourceGroupName}/providers/Microsoft.Compute/availabilitySets/{availabilitySetName}"

                }

              },

              "keyEncryptionKey": {

                "keyUrl": "aaaaaaaaaaaaa",

                "sourceVault": {

                  "id": "/subscriptions/{subscriptionId}/resourceGroups/{resourceGroupName}/providers/Microsoft.Compute/availabilitySets/{availabilitySetName}"

                }

              },

              "enabled": true

            },

            "image": {

              "uri": "https://{storageAccountName}.blob.core.windows.net/{containerName}/{vhdName}.vhd"

            },

            "writeAcceleratorEnabled": true,

            "diffDiskSettings": {

              "option": "Local",

              "placement": "CacheDisk"

            },

            "managedDisk": {

              "storageAccountType": "Standard_LRS",

              "diskEncryptionSet": {

                "id": "aaaaaaaaaaaaaaaaaaaaaaaaaaaa"

              },

              "securityProfile": {

                "securityEncryptionType": "VMGuestStateOnly",

                "diskEncryptionSet": {

                  "id": "aaaaaaaaaaaaaaaaaaaaaaaaaaaa"

                }

              },

              "id": "/subscriptions/{subscription-id}/resourceGroups/myResourceGroup/providers/Microsoft.Compute/disks/testingexcludedisk_OsDisk_1_74cdaedcea50483d9833c96adefa100f"

            },

            "deleteOption": "Delete"

          },

          "dataDisks": []

        },

        "osProfile": {

          "computerName": "Test",

          "adminUsername": "Foo12",

          "windowsConfiguration": {

            "provisionVMAgent": true,

            "enableAutomaticUpdates": true,

            "timeZone": "aaaaaaaaaaaaaaaaaaaa",

            "additionalUnattendContent": [

              {

                "passName": "OobeSystem",

                "componentName": "Microsoft-Windows-Shell-Setup",

                "settingName": "AutoLogon",

                "content": "aaaaaaaaaaaaaaaaaaaaaaaaaa"

              }

            ],

            "patchSettings": {

              "patchMode": "Manual",

              "enableHotpatching": true,

              "assessmentMode": "ImageDefault"

            },

            "winRM": {

              "listeners": [

                {

                  "protocol": "Http",

                  "certificateUrl": "aaaaaaaaaaaaaaaaaaaaa"

                }

              ]

            }

          },

          "secrets": [],

          "allowExtensionOperations": true,

          "customData": "aaaaaaaaaaaaaaaaaaaaaaa",

          "linuxConfiguration": {

            "disablePasswordAuthentication": true,

            "ssh": {

              "publicKeys": [

                {

                  "path": "aaaaaaaaaaaaaaaaaaaaaa",

                  "keyData": "aaa"

                }

              ]

            },

            "provisionVMAgent": true,

            "patchSettings": {

              "patchMode": "ImageDefault",

              "assessmentMode": "ImageDefault"

            }

          },

          "requireGuestProvisionSignal": true

        },

        "networkProfile": {

          "networkInterfaces": [

            {

              "id": "/subscriptions/{subscriptionId}/resourceGroups/{resourceGroupName}/providers/Microsoft.Network/networkInterfaces/{networkInterfaceName}",

              "properties": {

                "primary": true,

                "deleteOption": "Delete"

              }

            }

          ],

          "networkApiVersion": "2022-05-01",

          "networkInterfaceConfigurations": [

            {

              "name": "aaaaaaaa",

              "properties": {

                "primary": true,

                "deleteOption": "Delete",

                "enableAcceleratedNetworking": true,

                "disableTcpStateTracking": true,

                "enableFpga": true,

                "enableIPForwarding": true,

                "networkSecurityGroup": {

                  "id": "/subscriptions/{subscriptionId}/resourceGroups/{resourceGroupName}/providers/Microsoft.Compute/availabilitySets/{availabilitySetName}"

                },

                "dnsSettings": {

                  "dnsServers": [

                    "aaaaaaaaaaaaaaaaaaaaaaaa"

                  ]

                },

                "ipConfigurations": [

                  {

                    "name": "aaaaaaaa",

                    "properties": {

                      "subnet": {

                        "id": "/subscriptions/{subscriptionId}/resourceGroups/{resourceGroupName}/providers/Microsoft.Compute/availabilitySets/{availabilitySetName}"

                      },

                      "primary": true,

                      "publicIPAddressConfiguration": {

                        "name": "aaaaaaaaaaaaaaaaaa",

                        "properties": {

                          "idleTimeoutInMinutes": 23,

                          "deleteOption": "Delete",

                          "dnsSettings": {

                            "domainNameLabel": "aaaaa"

                          },

                          "ipTags": [

                            {

                              "ipTagType": "aaaaa",

                              "tag": "aaaaaaaaaaaaaaaaaaaaaaaaaaa"

                            }

                          ],

                          "publicIPPrefix": {

                            "id": "/subscriptions/{subscriptionId}/resourceGroups/{resourceGroupName}/providers/Microsoft.Compute/availabilitySets/{availabilitySetName}"

                          },

                          "publicIPAddressVersion": "IPv4",

                          "publicIPAllocationMethod": "Dynamic"

                        },

                        "sku": {

                          "name": "Basic",

                          "tier": "Regional"

                        }

                      },

                      "privateIPAddressVersion": "IPv4",

                      "applicationSecurityGroups": [

                        {

                          "id": "/subscriptions/{subscriptionId}/resourceGroups/{resourceGroupName}/providers/Microsoft.Compute/availabilitySets/{availabilitySetName}"

                        }

                      ],

                      "applicationGatewayBackendAddressPools": [

                        {

                          "id": "/subscriptions/{subscriptionId}/resourceGroups/{resourceGroupName}/providers/Microsoft.Compute/availabilitySets/{availabilitySetName}"

                        }

                      ],

                      "loadBalancerBackendAddressPools": [

                        {

                          "id": "/subscriptions/{subscriptionId}/resourceGroups/{resourceGroupName}/providers/Microsoft.Compute/availabilitySets/{availabilitySetName}"

                        }

                      ]

                    }

                  }

                ],

                "dscpConfiguration": {

                  "id": "/subscriptions/{subscriptionId}/resourceGroups/{resourceGroupName}/providers/Microsoft.Compute/availabilitySets/{availabilitySetName}"

                }

              }

            }

          ]

        },

        "provisioningState": "Succeeded",

        "additionalCapabilities": {

          "ultraSSDEnabled": true,

          "hibernationEnabled": true

        },

        "securityProfile": {

          "uefiSettings": {

            "secureBootEnabled": true,

            "vTpmEnabled": true

          },

          "encryptionAtHost": true,

          "securityType": "TrustedLaunch"

        },

        "diagnosticsProfile": {

          "bootDiagnostics": {

            "enabled": true,

            "storageUri": "aaaaaaaaaaaaaaaaaaaaa"

          }

        },

        "virtualMachineScaleSet": {

          "id": "/subscriptions/{subscriptionId}/resourceGroups/{resourceGroupName}/providers/Microsoft.Compute/availabilitySets/{availabilitySetName}"

        },

        "proximityPlacementGroup": {

          "id": "/subscriptions/{subscriptionId}/resourceGroups/{resourceGroupName}/providers/Microsoft.Compute/availabilitySets/{availabilitySetName}"

        },

        "priority": "Regular",

        "evictionPolicy": "Deallocate",

        "billingProfile": {

          "maxPrice": 26

        },

        "host": {

          "id": "/subscriptions/{subscriptionId}/resourceGroups/{resourceGroupName}/providers/Microsoft.Compute/availabilitySets/{availabilitySetName}"

        },

        "hostGroup": {

          "id": "/subscriptions/{subscriptionId}/resourceGroups/{resourceGroupName}/providers/Microsoft.Compute/availabilitySets/{availabilitySetName}"

        },

        "instanceView": {

          "platformUpdateDomain": 1,

          "platformFaultDomain": 29,

          "computerName": "aaaaaaaaaaaaaaaaaaaaaaaaaaaaa",

          "osName": "aaaaaaaaaaa",

          "osVersion": "aaaaaaaaaaaaaa",

          "hyperVGeneration": "V1",

          "rdpThumbPrint": "aaaaaaaaaaaaaaaaaaaaaaa",

          "vmAgent": {

            "vmAgentVersion": "aaaaaaaaaaaaaaaaaaaaaaaaaaaaa",

            "extensionHandlers": [

              {

                "type": "aaaaa",

                "typeHandlerVersion": "aaaaaaaaaaaaaaaaaaa",

                "status": {

                  "code": "aaa",

                  "level": "Info",

                  "displayStatus": "aaaaaaaaaaaaaaaaaaaaaaaa",

                  "message": "aaaaaaaaaaaaaaaaaaa",

                  "time": "2022-01-14T16:43:41.657Z"

                }

              }

            ],

            "statuses": [

              {

                "code": "aaa",

                "level": "Info",

                "displayStatus": "aaaaaaaaaaaaaaaaaaaaaaaa",

                "message": "aaaaaaaaaaaaaaaaaaa",

                "time": "2022-01-14T16:43:41.657Z"

              }

            ]

          },

          "maintenanceRedeployStatus": {

            "isCustomerInitiatedMaintenanceAllowed": true,

            "preMaintenanceWindowStartTime": "2022-01-14T16:43:41.682Z",

            "preMaintenanceWindowEndTime": "2022-01-14T16:43:41.682Z",

            "maintenanceWindowStartTime": "2022-01-14T16:43:41.682Z",

            "maintenanceWindowEndTime": "2022-01-14T16:43:41.682Z",

            "lastOperationResultCode": "None",

            "lastOperationMessage": "aa"

          },

          "disks": [

            {

              "name": "a",

              "encryptionSettings": [

                {

                  "diskEncryptionKey": {

                    "secretUrl": "aaaaaaaaa",

                    "sourceVault": {

                      "id": "/subscriptions/{subscriptionId}/resourceGroups/{resourceGroupName}/providers/Microsoft.Compute/availabilitySets/{availabilitySetName}"

                    }

                  },

                  "keyEncryptionKey": {

                    "keyUrl": "aaaaaaaaaaaaa",

                    "sourceVault": {

                      "id": "/subscriptions/{subscriptionId}/resourceGroups/{resourceGroupName}/providers/Microsoft.Compute/availabilitySets/{availabilitySetName}"

                    }

                  },

                  "enabled": true

                }

              ],

              "statuses": [

                {

                  "code": "aaa",

                  "level": "Info",

                  "displayStatus": "aaaaaaaaaaaaaaaaaaaaaaaa",

                  "message": "aaaaaaaaaaaaaaaaaaa",

                  "time": "2022-01-14T16:43:41.657Z"

                }

              ]

            }

          ],

          "extensions": [

            {

              "name": "aaaaaaaaaaaaaaaaaaaaaaaa",

              "type": "aaaaaaaaaaaaaaaaaaaaaaaa",

              "typeHandlerVersion": "aaaaaa",

              "substatuses": [

                {

                  "code": "aaa",

                  "level": "Info",

                  "displayStatus": "aaaaaaaaaaaaaaaaaaaaaaaa",

                  "message": "aaaaaaaaaaaaaaaaaaa",

                  "time": "2022-01-14T16:43:41.657Z"

                }

              ],

              "statuses": [

                {

                  "code": "aaa",

                  "level": "Info",

                  "displayStatus": "aaaaaaaaaaaaaaaaaaaaaaaa",

                  "message": "aaaaaaaaaaaaaaaaaaa",

                  "time": "2022-01-14T16:43:41.657Z"

                }

              ]

            }

          ],

          "vmHealth": {

            "status": {

              "code": "aaa",

              "level": "Info",

              "displayStatus": "aaaaaaaaaaaaaaaaaaaaaaaa",

              "message": "aaaaaaaaaaaaaaaaaaa",

              "time": "2022-01-14T16:43:41.657Z"

            }

          },

          "bootDiagnostics": {

            "consoleScreenshotBlobUri": "aaaaaaaaaaaaaaaaaaaaaaa",

            "serialConsoleLogBlobUri": "aaaaaaaaaaaaaaaaaaa",

            "status": {

              "code": "aaa",

              "level": "Info",

              "displayStatus": "aaaaaaaaaaaaaaaaaaaaaaaa",

              "message": "aaaaaaaaaaaaaaaaaaa",

              "time": "2022-01-14T16:43:41.657Z"

            }

          },

          "assignedHost": "aaaaaaaaaaaaaaaaaaaaaaaaaaaaa",

          "statuses": [

            {

              "code": "aaa",

              "level": "Info",

              "displayStatus": "aaaaaaaaaaaaaaaaaaaaaaaa",

              "message": "aaaaaaaaaaaaaaaaaaa",

              "time": "2022-01-14T16:43:41.657Z"

            }

          ],

          "patchStatus": {

            "availablePatchSummary": {

              "status": "Unknown",

              "assessmentActivityId": "aaaaaaaaaaaaaaaaaaa",

              "rebootPending": true,

              "criticalAndSecurityPatchCount": 22,

              "otherPatchCount": 25,

              "startTime": "2022-01-14T16:43:41.682Z",

              "lastModifiedTime": "2022-01-14T16:43:41.683Z",

              "error": {

                "details": [

                  {

                    "code": "aaaaaaaaaaaaaaaaaaaaa",

                    "target": "aaaaaa",

                    "message": "aaaaaaaaaaaaa"

                  }

                ],

                "innererror": {

                  "exceptiontype": "aaaaaaaaaaaaaaaaaaaaaaaaaaaaa",

                  "errordetail": "aaaaaaaaaaaaaaaaaaaaaaaaaaaa"

                },

                "code": "aaaaaa",

                "target": "aaaaaaaaa",

                "message": "aaa"

              }

            },

            "lastPatchInstallationSummary": {

              "status": "Unknown",

              "installationActivityId": "aaaaaa",

              "maintenanceWindowExceeded": true,

              "notSelectedPatchCount": 20,

              "excludedPatchCount": 1,

              "pendingPatchCount": 2,

              "installedPatchCount": 28,

              "failedPatchCount": 30,

              "startTime": "2022-01-14T16:43:41.683Z",

              "lastModifiedTime": "2022-01-14T16:43:41.683Z",

              "error": {

                "details": [

                  {

                    "code": "aaaaaaaaaaaaaaaaaaaaa",

                    "target": "aaaaaa",

                    "message": "aaaaaaaaaaaaa"

                  }

                ],

                "innererror": {

                  "exceptiontype": "aaaaaaaaaaaaaaaaaaaaaaaaaaaaa",

                  "errordetail": "aaaaaaaaaaaaaaaaaaaaaaaaaaaa"

                },

                "code": "aaaaaa",

                "target": "aaaaaaaaa",

                "message": "aaa"

              }

            },

            "configurationStatuses": [

              {

                "code": "aaa",

                "level": "Info",

                "displayStatus": "aaaaaaaaaaaaaaaaaaaaaaaa",

                "message": "aaaaaaaaaaaaaaaaaaa",

                "time": "2022-01-14T16:43:41.657Z"

              }

            ]

          }

        },

        "licenseType": "aaaaaaaaaaaaaa",

        "extensionsTimeBudget": "aaaaaaaaaaaaaaaaaaaaaa",

        "platformFaultDomain": 11,

        "scheduledEventsProfile": {

          "terminateNotificationProfile": {

            "notBeforeTimeout": "aaaaaaaaaaaaaaaaaaaaaaaaaaaa",

            "enable": true

          }

        },

        "userData": "aaaaaaaaaaaaaaaaaaa",

        "capacityReservation": {

          "capacityReservationGroup": {

            "id": "/subscriptions/{subscriptionId}/resourceGroups/{resourceGroupName}/providers/Microsoft.Compute/availabilitySets/{availabilitySetName}"

          }

        },

        "applicationProfile": {

          "galleryApplications": [

            {

              "tags": "aaaaa",

              "order": 4,

              "packageReferenceId": "aaaaaaaaaaaaaaaaaaaaaa",

              "configurationReference": "aaaaaaaaaaaaaaaaaaaaaaaaaaaaaa"

            }

          ]

        },

        "timeCreated": "2022-01-14T16:43:41.685Z"

      },

      "type": "Microsoft.Compute/virtualMachines",

      "location": "eastus",

      "tags": {},

      "id": "/subscriptions/{subscriptionId}/resourceGroups/{resourceGroupName}/providers/Microsoft.Compute/virtualMachines/{virtualMachineName}",

      "name": "{virtualMachineName}",

      "plan": {

        "name": "aaaaaaaaaaaaaaaaaa",

        "publisher": "aaaaaaaaaaaaaaaaa",

        "product": "aaaaaaaaaaaaaaaaaaaaaa",

        "promotionCode": "aaaaaaaaaaaaaa"

      },

      "resources": [

        {

          "properties": {

            "forceUpdateTag": "aaaaaaaaaaaaaaa",

            "publisher": "aaaaaaaaaaaaaaaa",

            "type": "aaaaaaaa",

            "typeHandlerVersion": "aaaaaaaaaaaa",

            "autoUpgradeMinorVersion": true,

            "enableAutomaticUpgrade": true,

            "settings": {},

            "protectedSettings": {},

            "provisioningState": "aaa",

            "instanceView": {

              "name": "aaaaaaaaaaaaaaaaaaaaaaaa",

              "type": "aaaaaaaaaaaaaaaaaaaaaaaa",

              "typeHandlerVersion": "aaaaaa",

              "substatuses": [

                {

                  "code": "aaa",

                  "level": "Info",

                  "displayStatus": "aaaaaaaaaaaaaaaaaaaaaaaa",

                  "message": "aaaaaaaaaaaaaaaaaaa",

                  "time": "2022-01-14T16:43:41.657Z"

                }

              ],

              "statuses": [

                {

                  "code": "aaa",

                  "level": "Info",

                  "displayStatus": "aaaaaaaaaaaaaaaaaaaaaaaa",

                  "message": "aaaaaaaaaaaaaaaaaaa",

                  "time": "2022-01-14T16:43:41.657Z"

                }

              ]

            },

            "suppressFailures": true,

            "protectedSettingsFromKeyVault": {

              "sourceVault": {

                "id": "/subscriptions/a53f7094-a16c-47af-abe4-b05c05d0d79a/resourceGroups/myResourceGroup/providers/Microsoft.KeyVault/vaults/kvName"

              },

              "secretUrl": "https://kvName.vault.azure.net/secrets/secretName/79b88b3a6f5440ffb2e73e44a0db712e"

            }

          },

          "id": "aaaaaaaaaaaaaaaaaaaaaaaaaaaaa",

          "name": "aaaaaaaaaaaaa",

          "type": "aaaaaaaaaaaaaaaaaaaaaaaaaaa",

          "location": "aaaaaaaaaaaaaaaa",

          "tags": {

            "key9428": "aaaaaaa"

          }

        }

      ],

      "identity": {

        "principalId": "aaaaaaaaaaaaaaaa",

        "tenantId": "aaaaa",

        "type": "SystemAssigned",

        "userAssignedIdentities": {

          "key5688": {

            "principalId": "aaaaaaaaaaaaaaa",

            "clientId": "aaaaaaaaaaa"

          }

        }

      },

      "zones": [

        "aaaaaa"

      ],

      "extendedLocation": {

        "name": "aaaa",

        "type": "EdgeZone"

      }

    }

  ],

  "nextLink": "a"

}

```

## Definitions ##

 |                                 |                                                                                                                                                                                                                                   |
|---------------------------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| `Additional Unattended Content` | Specifies additional XML formatted information that can be included in the Unattend.xml file, which is used by Windows Setup. Contents are defined by setting name, component name, and the pass in which the content is applied. |
| `Additional capabilities`         | Enables or disables a capability on the virtual machine or virtual machine scale set.                                                                                                                                             |
| `ApiError`                      | Api error.                                                                                                                                                                                                                        |
| `ApiErrorBase`                  | Api error base.                                                                                                                                                                                                                   |
| `ApplicationProfile`            | Contains the list of gallery applications that should be made available to the VM/VMSS                                                                                                                                            |
| `AvailablePatchSummary`         | Describes the properties of an virtual machine instance view for available patch summary.                                                                                                                                         |
| `BillingProfile`                | specifies the billing related details of a Azure spot VM Minimum api-version: 2019-03-01.                                                                                                                                         |
| `BootDiagnostics`               | Boot Diagnostics is a debugging feature which allows you to view Console Output and Screenshot to diagnose VM status.                                                                                                             |                                                                                                           |



Also see: [Perform maintenince](https://learn.microsoft.com/en-us/rest/api/compute/virtual-machines/perform-maintenance)

 [Restart](https://learn.microsoft.com/en-us/rest/api/compute/virtual-machines/restart)
 
[Retrieve Boot dianostic data](https://learn.microsoft.com/en-us/rest/api/compute/virtual-machines/retrieve-boot-diagnostics-data)
