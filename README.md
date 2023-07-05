#  GPG (GNU Privacy Guard)
## GPG is a free and open-source implementation of the OpenPGP encryption standard. It provides cryptographic privacy and authentication for data communication. GPG is commonly used for encrypting, decrypting.
## Generating a GPG Key Pair

- To use GPG, you need to generate a key pair consisting of a public key and a private key. The public key is used to encrypt messages that only the corresponding private key can decrypt, while the private key is kept secret and used for decrypting messages and signing files.<br/>

	    gpg --gen-key
  
- Export Public Key<br/>
You can now share your public key (public_key.asc) with others, allowing them to encrypt messages specifically for you. Remember to keep your private key secure and never share it with anyone.<br/>

	    gpg --armor --export <your_email_address> > public_key.asc

- Encrypting with GPG <br/>
You can encrypt files or messages using GPG by specifying the recipient's public key. The gpg --encrypt command, followed by options like --recipient and --output, allows you to encrypt a file or message and create an encrypted output file.<br/>

	    gpg --encrypt --armor --recipient "Recipient Name" --output encrypted_message.asc plaintext.txt
- Decrypting with GPG<br/>
To decrypt an encrypted file or message, you need the corresponding private key. The gpg --decrypt command, followed by the encrypted file as an argument, allows you to decrypt the file and retrieve the original content.<br/>

	    gpg --decrypt encrypted_message.asc
- Signing with GPG<br/>
GPG allows you to digitally sign files or messages using your private key. The signature provides authentication and verifies that the file or message has not been tampered with. The gpg --sign command, followed by the file to be signed, generates a detached signature file.<br/>

	    gpg --clear-sign --output signed_message.asc message.txt
- Verifying Signatures<br/>
To verify the authenticity and integrity of a signed file or message, you need the signer's public key. The gpg --verify command, followed by the signed file and the corresponding signature file, checks the signature and displays verification results.<br/>

	    gpg --verify signed_message.asc
- Import Other Public Key<br/>
Importing a public key allows you to encrypt messages for the corresponding key owner.<br/>

	    gpg --import public_key.asc
- Edit Trust Key<br/>
Editing a key allows you to perform operations like changing trust levels, adding signatures, or updating key properties.<br/>

	    gpg --edit-key keyID
trust
- Listing Key usage<br/>
Listing keys helps you view the existing public keys in your keyring.<br/>

	    gpg --list-keys

	    gpg --list-secret-keys
- Deleting Key<br/>

	    gpg --delete-secret-keys Keyname
	    gpg --delete-keys Keyname
