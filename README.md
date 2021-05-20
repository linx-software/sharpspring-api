# Sharpspring integration

## Overview

The provided sample includes:

- Creating your API key
- Configuring Linx with your API Key
- Running the sample functions

### Additional resources

- [Sharpspring API reference](https://help.sharpspring.com/hc/en-us/sections/115000320047-API)

---

## Dependencies

### Pre-requisites

- Linx Designer
- Sharpspring 'Admin' account

### Linx Designer

This solution was developed in the Linx Designer `v5.20.3.0`

---

## Setting up the sample

Generate API Key

1. Log into Sharpspring.
2. Click User **Menu** > **Settings** in SharpSpring's top toolbar.
3. Click **API Settings**, located under the _SharpSpring API_ section in the left panel.
4. Access your SharpSpring API keys under Account ID and Secret Key.
5. Click **Generate New API Keys** for new API keys.
6. Copy your 'Secret Key' (API Key) and 'Account ID'.

Configure Linx Solution

1. Open up the provided sample in your Linx Designer.
1. Open up the $.Settings editor.
1. Update the below $.Settings with your credentials:
   - SharpspringAccountId - your 'Account ID'.
   - SharpspringApiKey - your 'Secret Key'.
1. Save the Solution.

---

## Using the sample

---

### Authentication

Description: Request are authenticated via query parameters containing your credentials like below:

```json
[
  {
    "Name": "accountID",
    "Value": {
      "LinxExpression": "$.Settings.SharpspringAccountId"
    }
  },
  {
    "Name": "secretKey",
    "Value": {
      "LinxExpression": "$.Settings.SharpspringApiKey"
    }
  }
]
```

### Making requests

Description: Requests all made with the `POST` method, submitting a JSON request body containing the method, requestId and additional parameters.

Due to the particular formatting of the API request data for Sharpring, most requests will need their own request objects like below:

```json
* getLeads RequestData example *

{
   "method":"getLeads",
   "params":{
      "where":{
         "emailAddress":{
            "LinxExpression":"$.Parameters.email"
         },
         "id":{
            "LinxExpression":"$.Parameters.id"
         }
      },
      "limit":"5",
      "offset":"0"
   },
   "id":{
      "LinxExpression":"$.System.CurrentDateTime.ToString(\"yyyyMMddHHmmss\")"
   }
}
```

The `RequestData` objects used for each specific request are housed in their own nested folder.

```
[Sharpring]
|___________[Leads]
            |___________[GetLeads]
                         |___________[RequestData]
                         |___________GetLead
                         |___________GetLeads

```

---

### Using the sample

Several wrapper functions have created which involve the following:

- GetLeads: Returns all leads from Sharpspring.
- GetLead: Returns a single lead based on an `emailAddress` or `id`.
- GetLeadsForDataRange: Returns all leads updated in a given date range.
- GetEvents: Returns all events for a `leadID`.
- TestAll: Executes the above functions passing data from one into the other.
