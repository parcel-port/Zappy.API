#  Get the available shipping rates for Specific Carrier

Allows third-party systems to get a list of applicable shipping rate based on
the passed sender's address, recipient's address and parcel(s)’ dimensions.

- URL: /api/2.0/rate/getsinglecarrier
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

*CarrierId* - [Require. Carrier ID. If you do not fill in this field, you will not be able to query the carrier's quotation.]

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
- **insuredValueAmount** - [Required if international, insured value]
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

*Carrier Id*
<table>
  <tr>
    <th>ID</th>
    <th>Name</th>
  </tr>
  <tr>
    <td>NCP</td>
    <td>NZPost Domestic</td>
  </tr>
  <tr>
    <td>apinewph</td>
    <td>Post Haste</td>
  </tr>
  <tr>
    <td>fliway</td>
    <td>Fliway</td>
  </tr>
  <tr>
    <td>ft</td>
    <td>Aramex</td>
  </tr>
  <tr>
    <td>np</td>
    <td>NZPost International</td>
  </tr>
  <tr>
    <td>dhl</td>
    <td>DHL</td>
  </tr>
  <tr>
    <td>fedexapi</td>
    <td>FedEx</td>
  </tr>
  
</table>

## Response: 
Refer to the Example.

*Carrier and Carrier Method*  
*Notes: NZ Post Offline is available only if your account manager has enabled it for you. All carrier method IDs for NZ Post Offline have an "OFF" suffix (e.g., CPOLPOFF for the NZ Post Overnight Delivery service).
<table border="1" cellpadding="6" cellspacing="0">
  <thead>
    <tr>
      <th></th>
      <th>Carrier ID</th>
      <th>Carrier Name</th>
      <th>Carrier Method ID</th>
      <th>Service Description</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td rowspan="12">Domestic</td>
      <td rowspan="2">apinewph</td>
      <td rowspan="2">Post Haste</td>
      <td>apinewphft</td>
      <td>Overnight Delivery</td>
    </tr>
    <tr>
      <td>apinewphft2d</td>
      <td>2 Day Delivery</td>
    </tr>
    <tr>
      <td>ft</td>
      <td>Aramex</td>
      <td>ft_freight</td>
      <td>Standard Delivery Service</td>
    </tr>
    <tr>
      <td rowspan="9">NCP / NCPOFF</td>
      <td rowspan="9">NZ Post / NZ Post Offline</td>
      <td>CPOLE</td>
      <td>NZ Post Inter-Island Economy</td>
    </tr>
    <tr><td>CPOLP</td><td>NZ Post Overnight Delivery</td></tr>
    <tr><td>CPOLPPS</td><td>NZ Post Perishable Parcel</td></tr>
    <tr><td>CPOLTPA4</td><td>NZ Post Satchel A4</td></tr>
    <tr><td>CPOLTPA5</td><td>NZ Post Satchel A5</td></tr>
    <tr><td>CPOLTPDL</td><td>NZ Post Satchel DEL</td></tr>
    <tr><td>CPOLTPFS</td><td>NZ Post Satchel Foolscap</td></tr>
    <tr><td>CPOLTPLF</td><td>NZ Post Satchel Lineflow</td></tr>
    <tr><td>CPOLTPXL</td><td>NZ Post Satchel Extra Large</td></tr>
    <tr>
      <td rowspan="19">International</td>
      <td rowspan="11">np</td>
      <td rowspan="11">NZ Post</td>
      <td>ICOU</td>
      <td>Courier</td>
    </tr>
    <tr><td>IECON</td><td>Economy</td></tr>
    <tr><td>IECOP</td><td>Economy Plus</td></tr>
    <tr><td>IECOT</td><td>Economy Tracked</td></tr>
    <tr><td>ICOUSCN</td><td>Courier Select China</td></tr>
    <tr><td>ICOUSEAUN</td><td>Courier Select AU Exp Sig Required No ATL</td></tr>
    <tr><td>ICOUSEAUS</td><td>Courier Select AU Express Sig Required</td></tr>
    <tr><td>ICOUSSAUN</td><td>Courier Select AU Standard Sig w/o ATL</td></tr>
    <tr><td>ICOUSSAUS</td><td>Courier Select AU Standard Sig w/ ATL</td></tr>
    <tr><td>ICOUSSAUT</td><td>Courier Select AU Standard Tracked</td></tr>
    <tr><td>ICOUSUS</td><td>Courier Select US</td></tr>
    <tr>
      <td rowspan="4">dhl</td>
      <td rowspan="4">DHL</td>
      <td>DHL-E</td>
      <td>EXPRESS 9:00</td>
    </tr>
    <tr><td>DHL-M</td><td>EXPRESS 10:30</td></tr>
    <tr><td>DHL-P</td><td>EXPRESS WORLDWIDE</td></tr>
    <tr><td>DHL-Y</td><td>EXPRESS 12:00</td></tr>
    <tr>
      <td rowspan="4">fedexapi</td>
      <td rowspan="4">FedEx</td>
      <td>fedexapi_ie</td>
      <td>FedEx International Economy</td>
    </tr>
    <tr><td>fedexapi_intl1st</td><td>FedEx International First</td></tr>
    <tr><td>fedexapi_ip eod</td><td>FedEx International Priority</td></tr>
    <tr><td>fedexapi_ipe</td><td>FedEx International Priority Express</td></tr>
  </tbody>
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
  },
  "IsSignature": "0",
  "IsPhotoRequired":"0",
  "IsSaturday":"0",
  "IsDG": "0",
  "IsR18": "0",
  "CustomsCode":"",
  "CarrierId":"NCP"
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
                "carrierName": "CourierPost",
                "carrierMethodId": "CPOLPOFF",
                "totalPrice": 4.82,
                "totalGst": 0.73
            }
        ],
        "errors": {}
    }
}
```
