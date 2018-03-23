import sys, paramiko



hostname = '192.168.1.4'
password = 'xxxxxxxx'
command = 'cat h1'

username = 'xxxxxxx'
port = 22

try:
    client = paramiko.SSHClient()
    client.load_system_host_keys()
    client.set_missing_host_key_policy(paramiko.WarningPolicy)
    
    client.connect(hostname, port=port, username=username, password=password)

    stdin, stdout, stderr = client.exec_command(command)
    print (stdout.read())
    exit_status = stdout.channel.recv_exit_status()
    if exit_status == 0:
            print("command executed succesfully")
    else:
            print("command not executed successfully")

finally:
    client.close()
