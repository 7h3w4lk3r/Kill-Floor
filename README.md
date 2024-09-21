# Kill-Floor

Kill-Floor is an AV/EDR killer utilizing Avast’s “Anti Rootkit” driver. The code structure is designed to be adaptable for other BYOVD (Bring Your Own Vulnerable Driver) attack types. However, after a year, the included driver (`aswarpot.bin`) is heavily signatured by most security vendors. For effective use, consider replacing the driver with a less detectable alternative.

## Execution Flow

The Kill-Floor tool operates as follows:

1. Write the driver to disk (stored as an array within the file for convenience).
2. Create a service and load the driver.
3. Enter an infinite loop, taking snapshots of running processes.
4. Identify and terminate processes associated with known AV/EDR vendors.
5. Repeat.

## References

[Finding and Exploiting Process Killer Drivers with LOL for $3,000 (Alice Climent-Pommeret)](https://alice.climent-pommeret.red/posts/process-killer-driver/)  
[Vulnerable Antivirus Driver Used by Ransomware (OALabs)](https://www.youtube.com/watch?v=ViWLMfSwGVA)  
