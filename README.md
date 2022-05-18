## Baremetal Hardware Event Proxy / Operator

* Does the component require any special permissions, i.e. anything not provided by the restricted SCC in OpenShift?

No.

* Does it expose any endpoints reachable outside a cluster?

Yes. It exposes a TLS enabled webhook endpoint which receives POST event notifications from Redfish compliant devices.

* Does it handle any sensitive information?

No.

* Know when the component is:

    * Generally Available (GA): Baremetal Hardware Event Proxy is GA for 4.10.

    * Tech Preview: Baremetal Hardware Event Proxy Operator is Tech Preview for 4.10.