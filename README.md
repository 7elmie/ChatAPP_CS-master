# Client User Interface for Chat Server
# @Author : 7elmie
![HomePage](https://github.com/7elmie/ChatAPP_CS-master/blob/main/photo_2022-01-29_03-29-50.jpg)
## Project Information
Implement an user interface for the chat server. This GUI has IP, port and name input line, and able to broadcast, privatly send, receive, and display messages according to the server protocol of string format.
## Environment Requirement
- Python 3.6
- PyQt5
### Run the Server
```
python server.py --host 127.0.0.1 --port 33002
```
### Run the Client User Interface
```
python chat_v1.py
```
## Features
### General Design
- tabs for individual function: Home page or chat room
- chat room tab disabled until connection setup
- messagebox prompt to confirm exit, and disconnect before exit
### Home tab
- foolproof on connection/disconnection button: name column required, prevent repeat connecting/disconnecting
- unlimited remaking coonection
- unvalid port or unvalid IP, set to default IP 127.0.0.1 port 33002
- no worry refused connection, the exception code deal with it
### Chat Room tab
- message sending by either push GUI button or press keyboard enter
- clear the LineEdit widget after each message sent
- real-time received message display
- message column always scroll down to the newest message
- private message display on both sender and receiver, with color
- real-time updating of combobox and attendance list at receiving server broadcast
- once the receiver left before the private message sent, dispaly "Private message not delivered"
- window expanding space is preferd for message column
- EMOJI, that is what chat room ask for
## Screenshots
![HomePage](https://github.com/7elmie/ChatAPP_CS-master/blob/main/2022-04-25%20(2).png)
![HomePage](https://github.com/7elmie/ChatAPP_CS-master/blob/main/2022-04-25%20(9).png)
![HomePage](https://github.com/7elmie/ChatAPP_CS-master/blob/main/2022-04-25%20(10).png)
![HomePage](https://github.com/7elmie/ChatAPP_CS-master/blob/main/2022-04-25%20(11).png)


"# ChatAPP_CSmaster" 
