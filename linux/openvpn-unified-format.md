# OpenVPN Unified Format

The OpenVPN unified format allows you to combine all of the certificate authority, keys, certificates and configuration file that you would normally send separately to a client. Using the unified format you can replace the cert, tls-auth, key and ca directives with XML equivalents containing the file data. For example:

    ...
    key-direction 1
    <tls-auth>
    -----BEGIN OpenVPN Static key V1-----
    StaticKeyStuffs
    -----END OpenVPN Static key V1-----
    </tls-auth>
    ...

This is much easier to distribute than a zip file and an instruction set and can simply be imported on any device that supports OpenVPN.
