# HTTP PATCH File Upload Inspection Bypass (Under Coordination)

## Overview

This repository documents a security research finding related to file upload
inspection behavior when HTTP PATCH requests are used in a web gateway
environment. The purpose of this repository is to provide high-level
documentation under coordinated disclosure.

No exploit code or proof-of-concept payloads are provided.

---

## Test Environment Summary

The behavior was observed in a controlled test environment with the following
components:

- A simple HTTPS server deployed using **Caddy**
- A self-hosted file management service (**File Browser**) running behind the HTTPS server
- Client-side file uploads performed using **HTTP PATCH** requests
- Network traffic routed through a web content / security gateway

---

## Observed Behavior

In this configuration:

- File uploads performed via HTTP PATCH requests were successfully processed
  by the backend file service
- The file upload activity was not classified or logged as a file upload event
  by the web gateway
- No corresponding file upload visibility was observed at the gateway level

This behavior differs from file uploads performed using other HTTP methods
(e.g., POST), which may be handled differently depending on gateway policy and configuration.

---

## Security Considerations

This repository is intended for documentation and coordination purposes only.
It does not contain exploit tooling, payloads, or instructions intended for
operational abuse.

Detailed technical information has been shared with the affected vendor
through appropriate responsible disclosure channels.

---

## Disclosure Status

- Issue reported to vendor
- Under coordinated disclosure
- Public documentation provided for reference and tracking purposes

Further details may be disclosed following vendor coordination.

---

## Disclaimer

This project is provided for defensive security research and documentation
purposes only.
