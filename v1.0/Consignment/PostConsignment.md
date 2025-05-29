# Create a new consignment

Allows third-party systems to make consignments and get consignment tracking
numbers based on the passed shipping method id, sender's address, recipient's address
and parcel(s)’ dimensions. 

Endpoint: /api/1.0/consignment?client_id=786

*This API can only be called after the API authentication is approved (the correct
auth string has been passed). 

## Required Parameters:
* carrier_id [Optional, value from quotes e.g. "ph"]
* carrier_method_id [Require, value from quotes e.g. "phms"]
* carrier_method_code [Require, value from quotes e.g. "MS"]
* QuoteRequestID [Require, value from quotes]
* authority_to_leave [Optional, 0 or 1, 1 if authority to leave]
* is_signature [Optional depend on Carrier's quotes, 0 or 1, 1 if need signature]

*Parcels*
- **length** - [Require Length of the parcel cm]
- **width** - [Require Width of the parcel cm]
- **height** - [Require Length of the parcel cm]
- **weight** - [Require Weight of the parcel Kg]
- **volume** - [Optional Volume of the parcel]
- **kind** - [Optional default is 0, 1 if using satchel]
- **group_id** - [Optional add the satchel code if using satchel]
- **cust_ref** - [Optional reference of the item]
- **insurance_required** - [Require if International, true / false]
- **insured_value_amount** - [Require if International, insured value]
- **currency** - [Optional, Default NZD, insured value currency]
- **parcel_contents** [Require if International]
  - **description** - [Require if International, description of your products]
  - **quantity** - [Require if International, quantity of your products]
  - **weight_kg** - [Require if International, weight of your products]
  - **value** - [Require if International, value of your products]

*PickupAddress*
- **address_body** [Require, unit number + street number + street name]
- **address_city** [Require, city]
- **address_country** [Require, country code, e.g., "NZ" for NewZealand]
- **address_postcode** [Require, postcode]
- **address_suburb** [Require, suburb]
- **contact_name** [Require, contact name]
- **email** [Require, sender email]
- **company_name** [Optional, company name]
- **phone** [Optional, contact phone]
- **instruction** [Optional, instruction]

*DeliveryAddress*
- **address_body** [Require, unit number + street number + street name]
- **address_city** [Require, city]
- **address_country** [Require, country code, e.g., "NZ" for NewZealand]
- **address_postcode** [Require, postcode]
- **address_suburb** [Require, suburb]
- **contact_name** [Require, contact name]
- **email** [Optional, email]
- **company_name** [Optional, company name]
- **phone** [Require if International, contact phone]
- **instruction** [Optional, instruction]

*Booking*
- **pickup_option** [Require, 0 or 1, 0 if booking now]
- **instructions** [Optional, city]

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

## Example
Request
PUT https://api.zappy.nz/api/1.0/consignment?client_id=110

**Headers**
Content-Type: application/json;

**Authorization**
Bearer:bSEX9PltRH8uoHLmFdnt115OqEPPQTrrHpht6Bwq0yos9EW7o6vcBtrV23AF2TcuA8FJTabH_t9x2hDo_tP840QIXfUmg0AGmRBfRHfeTeCjBGrK4ezMuLQ0jsyoDAb3cxUhkMniuJHYfSWhKlvyuQZPDqAffr4ggCY9qiojTgRm1s-EubJZK941SrtXBmTQKnkAWcru5MmXQvm0ziNAfZ_JhCKGoNHhpmnJVfQvGYMQNjMRknoE6GZl63GFZZ9tjMz2ICBPqEJsX67fWOoB2adbr58hA72omCMgLaX-1-DhYjlEnb_qhGljklPL3Qo6ohgykA

**Body**
``` json
{
  "authority_to_leave": 0,
  "carrier_id": "ph",
  "carrier_method_id": "phtd",
  "carrier_method_code": "TD",
  "is_signature": 1,
  "QuoteRequestID": "ab98ccf7-655f-4e53-af99-395c65c962b3",
  "parcels": [
    {
      "length": 1,
      "height": 1,
      "width": 1,
      "weight": 1,
    }
  ],
  "DeliveryAddress": {
    "address_body": "17 Witbrock Crescent",
    "address_city": "Christchurch",
    "address_country": "NZ",
    "address_postcode": 8053,
    "address_suburb": "Burnside",
    "contact_name": "Alice"
  },
  "PickupAddress": {
    "address_body": "12 Pitt Street",
    "address_city": "Auckland",
    "address_country": "NZ",
    "address_postcode": 1010,
    "address_suburb": "Auckland Central",
    "contact_name": "bob",
    "email": "bob@domain.com"

  },
  "booking":{
      "pickup_option": 1,
  }
}
```
**Responses**
A JSON encoded string contains all the valid shipping methods with shipping method ids.
The requestID need to be added in the request when you create a consignment, and it will be expired.

``` json
{
    "message": "",
    "isSuccess": true,
    "errorMessages": {},
    "consignmentRef": [
        "007860396061"
    ],
    "consignmentLocalIDs": [
        396061
    ],
    "consignmentRefEncode": [
        "SqzdUGp2YsOsMgN3e9WEBw=="
    ],
    "consignmentLabelRef": [
        "39U3HK"
    ],
    "consignmentTrackinglRef": [
        "00894210320451606683"
    ],
    "batchOrderId": null,
    "totalPrice": 0.00,
    "totalTax": 0.00
}
```

***
