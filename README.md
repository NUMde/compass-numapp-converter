# compass-numapp-converter
The repository for converting questionnaire responses from compass-numapp-downloader to .csv files

## Short description
This tool is an extension to COMPASS Questionnaire Response Downloader. It flattens the hierarchical structure of a questionnaire to a tabulation.
 
## Functionality
The script reads a decrypted questionnaire response, which is provided by the user. It spreads out the JSON object and keeps all other columns as they are. 
Kept columns are:
- UUID
- SubjectId
- QuestionnaireId
- Version
- AbsendeDatum
- ErhaltenDatum
 
Each question will generate a new column using the "definition" field as the header. If this field is missing, the "linkID" is used as fallback. For each value, the "answer" field will be decoded to a string, as it contains one of the following types:
- valueString
- valueInteger
- valueCoding
- valueBoolean
- valueDate
 
As there might be multiple questionnaire types in one response file, the script generates one file for each type, named after the field "questionnaire".

## Getting Started
Download Numcompass Converter.html and open with a Webbrowser. Click the "Choose File" button and select your decrypted questionnaire response file. Then click ok and receive all files as downloads. You may have to allow multiple file download to your browser.
 
Tested with:
- firefox 105
- chrome 105
- edge 106
