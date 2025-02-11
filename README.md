# Peer-to-Peer Chat Application

This project is a peer-to-peer chat application using UDP and TCP ports. It consists of four main components: `Service_Announcer`, `Peer_Discovery`, `Chat_Responder`, and `Chat_Initiator`. The application is developed for macOS and requires the `pycryptodome` library for encryption.

## Installation

Before running the application, ensure you have the required dependencies installed:

```sh
pip install pycryptodome
```

## Application Flow

### 1. Running `Service_Announcer.py`
- Uses a UDP socket to get the local IP address.
- Asks for the username and stores it in `users.json` along with the IP address and timestamp.

### 2. Running `Peer_Discovery.py`
- Reads `users.json` and maintains an array of user statuses.
- Checks user statuses every 8 seconds and displays their online/offline status along with the last seen timestamp.

### 3. Running `Chat_Responder.py`
- Works as a server, displaying a message when started.
- Waits for `Chat_Initiator.py` to establish a connection.
- Communicates with `Chat_Initiator.py` in either secure (encrypted) or unsecured mode.
- Stores chat logs in `chat_history.txt`.

### 4. Running `Chat_Initiator.py`
- Works as a client, displaying available online users.
- Prompts the user to choose whom to chat with and retrieves their IP address.
- Provides an option for encrypted communication.
- Encrypts and decrypts messages using `pycryptodome` if encryption is selected.
- Stores messages in `chat_history.txt`.

## Chat Security
- If encryption is enabled, messages are securely encrypted before transmission and decrypted upon receipt.
- Uses `pycryptodome` for encryption.

## Ready to Chat!
Once all steps are followed, peers can chat anytime securely or in plaintext.

---
