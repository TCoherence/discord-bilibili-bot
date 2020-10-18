# discord-bilibili-bot
This is a repo for create a discord bot which can play songs from Bilibili.

Manual Forked from: https://github.com/Neet-Nestor/Discord-Bilibili-Bot 
Made a little changes from the original one because of some errors.

# Issues I have:
1. Requirement conflict:
```
ERROR: Cannot install pynacl==1.2.1 and discord-py[voice] 1.2.5 because these package versions have conflicting dependencies.
```
discord.py[voice] 1.2.5 depends on pynacl 1.3.0 while we requires pynacl 1.2.1 which is imcompatible, it might have something to do with version change during the time so i change it to 1.3.0 manually. And it solves without any other issues.Though this error disappear later for unknown reason…

2. File not found error:
```
FileNotFoundError: [Errno 2] No such file or directory: 'config/example_permissions.ini'
```
go to the MusicBot original page and copy that file

3. Voice channel play voice failure
```future: <Task finished coro=<VoiceClient._create_socket() done, defined at /Users/yanghanzhi/anaconda3/lib/python3.7/site-packages/discord/voice_client.py:171> exception=gaierror(8, 'nodename nor servname provided, or not known')>
Traceback (most recent call last):
  File "/Users/yanghanzhi/anaconda3/lib/python3.7/site-packages/discord/voice_client.py", line 190, in _create_socket
    self.endpoint_ip = socket.gethostbyname(self.endpoint)
socket.gaierror: [Errno 8] nodename nor servname provided, or not known
```
refer to this issue PR https://github.com/Rapptz/discord.py/pull/5188 , I choose the first one since it makes more sense for me at this point and it do resolve my issue
