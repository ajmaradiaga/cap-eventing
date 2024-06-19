# CAP Eventing with Event Mesh capability in SAP Integration Suite
CAP app to demonstrate eventing with SAP Event Mesh

This project contains 3 separate CAP applications, to run locally, but connecting to the Event Mesh capability part of SAP Integration Suite for eventing.

## EMIS Setup
Make sure the Event Mesh capability is active (see https://help.sap.com/docs/integration-suite/sap-integration-suite/initiating-event-mesh?locale=en-US).
When creating the Event Mesh Service messaging client instance you have to provide a NAME, and afterward you create a binding also with a NAME. The binding will provide you with the necessary credentials to connect to the Event Mesh capability.


## Usage

To connect to the Event Mesh capability you need to include the contents of the binding in your default-env.json file, as below:

```json
{
    "VCAP_SERVICES": {
        "enterprise-messaging": [
            {
                "label": "enterprise-messaging",
                "credentials": { ... }
            }
        ]
    }
}
```

Terminal 1 (sending events):
```
cd emitter

npm install
cds watch --profile hybrid --port 4005
```
