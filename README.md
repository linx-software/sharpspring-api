# SharpSpring integration

## Description
Integration template between the SharpSpring marketing automation platform and Linx.

## Installation
### Pre-requisites

- Linx Designer
- Sharpspring 'Admin' account

### Generate API Key

1. Log into Sharpspring.
2. Click User **Menu** > **Settings** in SharpSpring's top toolbar.
3. Click **API Settings**, located under the _SharpSpring API_ section in the left panel.
4. Access your SharpSpring API keys under Account ID and Secret Key.
5. Click **Generate New API Keys** for new API keys.
6. Copy your 'Secret Key' (API Key) and 'Account ID'.

### Configure Linx Solution

1. Open up the provided sample in your Linx Designer.
1. Open up the $.Settings editor.
1. Update the below $.Settings with your credentials:
   - SharpspringAccountId - your 'Account ID'.
   - SharpspringApiKey - your 'Secret Key'.
1. Save the Solution.


## Usage

The below functions can be used to retrieve data from the API.

- GetLeads: Returns all leads from Sharpspring.
- GetLead: Returns a single lead based on an `emailAddress` or `id`.
- GetLeadsForDataRange: Returns all leads updated in a given date range.
- GetEvents: Returns all events for a `leadID`.
- TestAll: Executes the above functions passing data from one into the other.

## Contributing

For questions please ask the [Linx community](https://linx/software/community) or use the [Slack channel](https://linxsoftware.slack.com/archives/C01FLBC1XNX). 

## License

[MIT](https://github.com/linx-software/template-repo/blob/main/LICENSE.txt)


