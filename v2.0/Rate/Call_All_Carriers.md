#  Get available shipping rates

Allows third-party systems to get a list of applicable shipping rate based on
the passed sender's address, recipient's address and parcel(s)’ dimensions.

- URL: /api/2.0/rate
- Http Method: POST

*This API can only be called after the API authentication is approved (the correct
auth string has been passed).

## Required Parameters:
*isSignature* - [Optional, default is '*0*', '*1*' if signature required]

*isSaturday* - [Optional, default is '*0*', '*1*' if saturday delivery]

*isPhotoRequired* - [Optional, default is '*0*', '*1*' if photo required. mutually exclusive with signature]

*isDG* - [Optional, default is '*0*', '*1*' if sending DG. DG Account is required if sending DG, please contact our customer service for more information.]

*isR18* - [Optional, default is '*0*', '*1*' if Age Restricted]

*customsCode* - [Optional. Identification number assigned by overseas tax authorities. For example: IOSS Number (EU),EORI number (UK and EU),ABN/ABR(Australia).]

*parcels* - [Required, a list of parcel]
- **kind** - [Optional, default is '*0*', '*1*' if using satchel]
- **length** - [Required if not using satchel, length of the parcel cm]
- **width** - [Required if not using satchel, width of the parcel cm]
- **height** - [Required if not using satchel, height of the parcel cm]
- **weight** - [Required, weight of the parcel Kg]
- **satchelCode** - [Required if using satchel, see the following table of *Zappy satchel list* ]
- **custRef** - [Optional reference of the item]
- **packageName** - [Optional custom package name]
- **insuranceRequired** - [Required if international, true / false]
- **insuredValueAmount** - [Required if InsuranceRequired is true: the insured value. Be aware that extra charges may apply if the insuredValueAmount exceeds the carrier’s StandardCompensationCover.]
- **currency** - [Optional, currency of the insuredValueAmount]
- **contentType** - [Optional, choose a code from the 'Content Type' list below. Only apply for NZPost International services.]
- **packageContents** - [Required if international, a list of item in the parcel]
  - **hsTariffCode** [Required, HS tariff code]
  - **description** [Required, description of item]
  - **quantity** [Required, quantity of item]
  - **weight** [Required, weight of item]
  - **contentValue** [Required, value of item]

*deliveryAddress*
- **addressBody** [Require, unit number + street number + street name]
- **addressSuburb** [Require, suburb]
- **addressCity** [Require, city]
- **addressPostcode** [Require, postcode]
- **contactName** [Require, contact name]
- **addressUnit** [Optional, unit number]
- **addressBuilding** [Optional, building]
- **email** [Require, sender email]
- **phone** [Optional, contact phone]
- **companyName** [Optional, company name] 
- **instruction** [Optional, instruction]
- **addressLat** [Optional, latitude]
- **addressLng** [Optional, longitude]
- **isCommercial** [Optional, is commercial address]

*pickupAddress*
- **addressBody** [Require, unit number + street number + street name]
- **addressSuburb** [Require, suburb]
- **addressCity** [Require, city]
- **addressPostcode** [Require, postcode]
- **contactName** [Require, contact name]
- **addressUnit** [Optional, unit number]
- **addressBuilding** [Optional, building]
- **email** [Require, sender email]
- **phone** [Optional, contact phone]
- **companyName** [Optional, company name. Required for the courier 'Fliway'.] 
- **instruction** [Optional, instruction]
- **addressLat** [Optional, latitude]
- **addressLng** [Optional, longitude]
- **isCommercial** [Optional, is commercial address]

*Zappy satchel list*
<table>
  <tr>
    <th>Satchel name</th>
    <th>code</th>
  </tr>
  <tr>
    <td>Satchel 130x240 DLE Letter Size</td>
    <td>dle</td>
  </tr>
  <tr>
    <td>Satchel 185x280 A5 Size</td>
    <td>a5</td>
  </tr>
  <tr>
    <td>Satchel 250x325 A4 Size</td>
    <td>a4</td>
  </tr>
  <tr>
    <td>Satchel 275x380 Foolscap Size</td>
    <td>fs</td>
  </tr>
  <tr>
    <td>Satchel 325x440 A3 Size</td>
    <td>a3</td>
  </tr>
  <tr>
    <td>Satchel 395x440 Lineflow Size</td>
    <td>lf</td>
  </tr>
  <tr>
    <td>Satchel 445x440 Extra Large Size</td>
    <td>xl</td>
  </tr>
  <tr>
    <td>Satchel 450x610 A2 Size</td>
    <td>a2</td>
  </tr>
</table>

*Content type*
<table>
  <tr>
    <th>Code</th>
    <th>Description</th>
  </tr>
  <tr>
    <td>11</td>
    <td>Sales of goods</td>
  </tr>
  <tr>
    <td>91</td>
    <td>Documents</td>
  </tr>
  <tr>
    <td>21</td>
    <td>Returned Goods</td>
  </tr>
  <tr>
    <td>31</td>
    <td>Gift</td>
  </tr>
  <tr>
    <td>32</td>
    <td>Commercial Sample</td>
  </tr>
  <tr>
    <td>999</td>
    <td>Other (default)</td>
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

**Request Body**
``` json
{
  "parcels": [
    {
      // "kind": "1",
      // "satchelCode": "a4",
      "length": "20",
      "height": "20",
      "width": "30",
      "weight": "0.5",
      "custRef": "09-2101-00021",
      "packageName": "No1-white box"
    }
  ],
  "deliveryAddress": {
    "addressBody": "24 Ryland Park RD 5",
    "addressPostcode": "5575",
    "addressSuburb": "Levin",
    "addressCity": "Levin",
    "addressCountry": "NZ",
    "contactName": "test",
    "email": "123@456.com",
    "phone": "02101020304"
  },
  "pickupAddress": {
    "addressBody": "6 Heremai Street",
    "addressPostcode": "0612",
    "addressSuburb": "Henderson",
    "addressCity": "Auckland",
    "addressCountry": "NZ",
    "contactName": "test",
    "email": "123@456.com",
    "phone": "02101020304",
    "companyName": "Zappy"
  }
}
```
**Responses**  
A JSON encoded string contains all valid shipping rates with a price and a shipping method id.  
The rates will be expired in 15 minutes.  
Choose a carrier from the list of rate and [create a consignment](Consignment/README.md) using it's carrierMethodId and the quoteRequestId.

``` json
{
    "isSuccess": true,
    "data": {
        "quoteRequestId": "98a13230-583d-4cc3-8278-c597dd30cfd5",
        "expiryDate": "2023-11-10T08:58:28.4476751+13:00",
        "deliveryAddressIsRural": "1",
        "rates": [
            {
                "carrierName": "Fastway",
                "carrierMethodId": "ft_freight",
                "totalPrice": 7.01,
                "totalGst": 1.05
            },
            {
                "carrierName": "CourierPost",
                "carrierMethodId": "CPOLP",
                "totalPrice": 4.82,
                "totalGst": 0.73
            },
            {
                "carrierName": "CourierPost",
                "carrierMethodId": "CPOLPOFF",
                "totalPrice": 4.82,
                "totalGst": 0.73
            }
        ],
        "errors": {
            "postHaste": [
                "{\"DeliveryAddress.Lat\":[\"The Lat field is required.\"],\"DeliveryAddress.Lon\":[\"The Lon field is required.\"]}"
            ],
            "castleParcels": [
                "{\"DeliveryAddress.Lat\":[\"The Lat field is required.\"],\"DeliveryAddress.Lon\":[\"The Lon field is required.\"]}"
            ],
            "kiwiExpress Oversize": [
                "Please check the package details. The weight should be above 25kg and below 50kg(inc.), or the volumn should be above 0.125m³ and below 0.3m³(inc.)."
            ],
            "nw": [
                "Not available in this route"
            ]
        }
    }
}
```







