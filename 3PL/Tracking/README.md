# Get Tracking History – Deprecated. Stock levels are now updated via webhook. Please contact us to arrange setup.

Request for tracking history of an outwards order.

- URL: /Outwards/{ReferenceNumber}
- Http Method: GET

*This API can only be called after the API authentication is approved (the correct
auth string has been passed). 

## Required Parameters:
* ReferenceNumber [Require, the '*ReferenceNumber*' passed while creating the outwards request.]

## Response：
*Data* - [A Json Object.]
- **DeliveryOrPickup** - [Delivery / Pickup]
- **ProcessStatus** - [Refer to the 'Process status code table' below.]
- **StatusDescription** - [A description for 'ProcessStatus'.]
- **CancelReasonCode** - [Refer to the 'Cancel reason code table' below. Nullable.]
- **CancelReason** - [A description for 'CancelReasonCode'. Nullable.]
- **DatePickedUpUtc** - [A UTC datetime indicates when the parcel was picked up by carrier or recipient. Nullable.]
- **InWarehouse** - [A list of process statuses that occurred in the warehouse.]
  - **Status**  - [Refer to the 'Process status code table' below.]
  - **StatusDescription**
  - **StatusTimeUtc**
- **Tracking** - [A list of tracking information. Nullable.]
  - **Carrier** 
  - **TrackingRef**
  - **TrackingLink**
  - **Statuses** - [A list of tracking statuses.]
    - **Status**  - [Refer to the 'Delivery status table' below]
    - **StatusDescription**
    - **StatusTimeUtc**

*Process status code table*
<table>
  <tr>
    <th>Process Status Code</th>
    <th>Description</th>
  </tr>
  <tr>
    <td>0</td>
    <td>Not submitted yet. Only if the outwards request is created on the client-side pages.</td>
  </tr>
  <tr>
    <td>1</td>
    <td>Waiting to be processed. The default status if the outwards request is created via API</td>
  </tr>
  <tr>
    <td>3</td>
    <td>Currently being processed</td>
  </tr>
  <tr>
    <td>4</td>
    <td>Ready for pick up</td>
  </tr>
  <tr>
    <td>5</td>
    <td>Picked. Waiting for packing</td>
  </tr>
  <tr>
    <td>6</td>
    <td>Picked up</td>
  </tr>
  <tr>
    <td>7</td>
    <td>Partially delivered</td>
  </tr>
  <tr>
    <td>8</td>
    <td>Delivered</td>
  </tr>
  <tr>
    <td>9</td>
    <td>Cancelled</td>
  </tr>
</table>

*Cancel reason code table*
<table>
  <tr>
    <th>Cancel Reason Code</th>
    <th>Description</th>
  </tr>
  <tr>
    <td>0</td>
    <td>As requested</td>
  </tr>
  <tr>
    <td>1</td>
    <td>Insufficient Stock</td>
  </tr>
  <tr>
    <td>8</td>
    <td>Custom Cancelled</td>
  </tr>
  <tr>
    <td>9</td>
    <td>Others</td>
  </tr>
</table>

*Delivery status table*
<table>
  <tr>
    <th>Delivery Status</th>
    <th>Description</th>
  </tr>
  <tr>
    <td>1</td>
    <td>Picked Up</td>
  </tr>
  <tr>
    <td>6</td>
    <td>Delivered</td>
  </tr>
</table>

## Example

**Request Headers**
```
Content-Type: application/json;
```

**Request Authorization**
```
Bearer:XlES6IXxqQZwo37CoB9ydlZmWQV84VdNhv-MF0WXpr9SUJqv3bL5CsBIDTqrDildBRBkzo6J2VmbdGyZu7yBGANnCUVMDzxelycDQXn9xBxqobDBAVs70nslc4C90PJ6jmtEI56U5SD8ms5c7ubKOa6DR0rLb_GTY4kXitqHPsPpCaUKckwGSIyCwGeZcAx60A50Na2CTISg5CfCGFTTAOQ6znVRLkJIb4fbbI87iYkBLDbQb2S09iFAqMc0odR9lpziU3BS5y41fZBXHwUUCEwk2-EFs7RFS_L6WT0zRcBSlwluqGchGuiLCg7d3NT1bZEPcf8u_BQFc_Wnkjd_pf4RHdt7pBHa6mgDib5ao1hugdE5z
```

**Responses**
``` json
{
    "IsSuccess": true,
    "Data": {
        "DeliveryOrPickup": "Delivery",
        "ProcessStatus": "6",
        "StatusDescription": "Picked up",
        "CancelReasonCode": null,
        "CancelReason": null,
        "DatePickedUpUtc": "2024-04-09T02:20:13",
        "InWarehouse": [
            {
                "Status": "3",
                "StatusDescription": "Currently being processed",
                "StatusTimeUtc": "2024-04-08T22:06:08.0106716"
            },
            {
                "Status": "4",
                "StatusDescription": "Ready for pick up",
                "StatusTimeUtc": "2024-04-08T23:03:17.0864156"
            }
        ],
        "Tracking": [
            {
                "Carrier": "Fastway - ft_freight",
                "TrackingRef": "MX00xxxxxxxx",
                "TrackingLink": "https://www.aramex.co.nz/tools/track?l=MX00xxxxxxxx",
                "Statuses": [
                    {
                        "Status": "1",
                        "StatusDescription": "Picked Up",
                        "StatusTimeUtc": "2024-04-09T02:20:13"
                    }
                ]
            }
        ]
    }
}
```
