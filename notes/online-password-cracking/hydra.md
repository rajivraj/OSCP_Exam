# Hydra

* We could crack a wide range of protocol authentication schemes using hydra.
* We should be very careful with the hydra, as mistake in one of the parameter will not execute hydra.
* 
## Username enumeration

![&quot;-e n&quot; option in hydra](../../.gitbook/assets/image%20%2840%29.png)

## Example : HTTP Basic authorization with base64

* -C option in hydra accepts a list of : seperate username:password list. It will automatically url encode to base64.
* You can validate this by setting burp suite proxy.

## Troubleshooting 1

![](../../.gitbook/assets/image%20%2855%29.png)

To resolve this correct your "grep condition" which is your last parameter of hydra. To correct use the error from the webpage for the desired differentiation.

![](../../.gitbook/assets/image%20%2825%29.png)

The correct condition seems to be "ERROR" or "incorrect"

