<div align="center">

# Telnyx Node Demo Spec

![Telnyx](logo-dark.png)

The Open API specification for "THE" Telnyx Demo application

</div>

## Versions

| Version                     | Description                                  |
|:----------------------------|:---------------------------------------------|
| [v1](cpaas-example.v1.json) | Basic number search & order, Basic Messaging |

## Relevant Documentation

The full documentation and tutorial is available on [developers.telnyx.com](https://developers.telnyx.com/)

## Capabilities

* [Phone Numbers](#phone-numbers)
  * Search phone numbers by areaCode, City, State
  * Order phone number with a "reference"
* [Messaging](#messaging)
  * Send SMS / MMS from a Telnyx Number
  * Receive inbound/outbound Message Callbacks

## Phone Numbers

### Searching Numbers

Proxies the request to the Telnyx API and reduce the response to an array of phone numbers in e164 format.

It's expected the user will pick one of the numbers in the response and order that number

### Ordering Numbers

Proxies the number order request to the Telnyx API and return the response if successful

## Messaging

### Sending Messages

Proxies the message request to the Telnyx messaging API and return the message id as well as the request information.  The request to Telnyx should be set to receive the outbound status message (DLR) to the corresponding webhook.

### Webhooks

Receives webhooks from Telnyx indicating outbound status updates (DLRs) or inbound messages.

Responds to the Webhook request from Telnyx with a `200-ok` response

#### Outbound Status DLR

Print the ID and Status to the console

### Receiving messages

Print the ID and text of the message to the console.

Send a "reply" (new message) to the phone number with the text: "Thanks for your message!"