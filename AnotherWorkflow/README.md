# Replace Data in Google Docs from n8n Form

This n8n workflow automates the process of collecting form data, formatting it, and replacing placeholders in a Google Docs template with the submitted data. It is designed to streamline the creation of customized documents based on user input.

## Workflow Overview

1. **Form Trigger**: Captures form submissions with required fields.
2. **Copy Template File**: Creates a copy of a predefined Google Docs template.
3. **Format Form Data**: Processes the form data into a key-value structure.
4. **Format Data for Google Docs API**: Converts the formatted data into a structure compatible with the Google Docs API.
5. **Replace Data in Google Doc**: Sends a request to the Google Docs API to replace placeholders in the document with the submitted form data.

## Workflow Nodes

### 1. Form Trigger
- **Node Name**: `Form`
- **Purpose**: Captures form submissions.
- **Key Parameters**:
  - `formTitle`: "Form"
  - `formFields`: Includes a required field labeled `name`.

### 2. Copy Template File
- **Node Name**: `Copy template file`
- **Purpose**: Copies a Google Docs template for customization.
- **Key Parameters**:
  - `fileId`: ID of the Google Docs template.
  - `name`: Sets the name of the copied file based on the form submission.

### 3. Format Form Data
- **Node Name**: `Format form data`
- **Purpose**: Converts form data into a key-value structure for processing.
- **Key Parameters**:
  - JavaScript code processes the form data into an array of objects with `key` and `value` properties.

### 4. Format Data for Google Docs API
- **Node Name**: `Format form data to Google Doc API`
- **Purpose**: Prepares the formatted data for the Google Docs API.
- **Key Parameters**:
  - JavaScript code generates `replaceAllText` requests for each form field.

### 5. Replace Data in Google Doc
- **Node Name**: `Replace data in Google Doc`
- **Purpose**: Sends a batch update request to the Google Docs API to replace placeholders in the document.
- **Key Parameters**:
  - `url`: Google Docs API endpoint for batch updates.
  - `bodyParameters`: Includes the formatted data as `requests`.

## Notes

- **Authentication**: 
  - The form requires Basic Authentication to prevent unauthorized access.
  - The Google Docs and Google Drive nodes use OAuth2 credentials for authentication.
- **Placeholders in Template**: Use `{{fieldName}}` in the Google Docs template to define placeholders that will be replaced with form data.

## Example Use Case

1. A user submits a form with their name and other details.
2. The workflow copies a Google Docs template.
3. The submitted data is formatted and used to replace placeholders in the copied document.
4. The customized document is ready for use.

## Sticky Notes in Workflow

- **Sticky Note 1**: Explains how form fields are converted into variables for use in the Google Docs template.
- **Sticky Note 2**: Provides instructions for setting up authentication for the Google Docs API.

## Prerequisites

- An active Google account with access to Google Docs and Google Drive.
- OAuth2 credentials set up in n8n for Google Drive and Google Docs.
- A Google Docs template with placeholders (e.g., `{{name}}`).

## How to Use

1. Import the workflow JSON file into your n8n instance.
2. Configure the form fields as needed.
3. Set up the required OAuth2 credentials for Google Drive and Google Docs.
4. Run the workflow and submit the form to generate a customized Google Doc.

## Troubleshooting

- Ensure the Google Docs template ID is correct and accessible.
- Verify that the placeholders in the template match the form field labels.
- Check that the OAuth2 credentials are properly configured in n8n.

## License

This workflow is provided under the MIT License.
