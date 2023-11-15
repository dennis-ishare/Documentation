Versions
========

Retrieves active and planned versions of iSHARE. By default returns current state. Server response is an iSHARE signed JSON Web Token. Please refer to the models 'jwt_header' and 'jwt_payload_versions_token' which indicate what the decoded response will look like.

Parameters
~~~~~~~~~~
No Parameters


Response
--------

200
    | OK

::

    < Content-Type: application/json

{
  "versions_token": {
    "iss": "EU.EORI.NL123456789",
    "sub": "EU.EORI.NL123456789",
    "aud": "EU.EORI.NL123456789",
    "jti": "378a47c4-2822-4ca5-a49a-7e5a1cc7ea59",
    "exp": 1504684475,
    "iat": 1504683475,
    "versions_info": {
      "version_name": "3.0.0",
      "valid_from": "2030-07-04T08:00:00Z",
      "valid_to": "2050-01-04T08:00:00Z",
      "version_status": "planned"
    }
  }
}

Extensions
~~~~~~~

``x-operation-settings``
    | **String**.
    | {"CollectParameters":false,"AllowDynamicQueryParameters":false,"AllowDynamicFormParameters":false,"IsMultiContentStreaming":false,"ErrorTemplates":{},"SkipAdditionalHeaders":false}

``x-unitTests``
    | **String**.
    |[{"request":{"method":"GET","uri":"/versions"},"expectedResponse":{"x-allowExtraHeaders":true,"x-bodyMatchMode":"NONE","x-arrayOrderedMatching":false,"x-arrayCheckCount":false,"x-matchResponseSchema":true,"statusCode":"200","headers":{"Content-Type":"application/json"}},"x-testShouldPass":true,"x-testEnabled":true,"x-testName":"Test /versions","x-testDescription":"Retrieves active and planned versions of iSHARE. By default returns current state. Server response is an iSHARE signed JSON Web Token. Please refer to the models 'jwt_header' and 'jwt_payload_versions_token' which indicate what the decoded response will look like."}]
