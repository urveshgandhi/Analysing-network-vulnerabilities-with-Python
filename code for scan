import datetime
import socket


while True:

    target_user = input("Pick a host: ")
    try:
        target_ip = socket.gethostbyname(target_user)
        adr = socket.gethostbyaddr(target_ip)
        print(adr)
        break
    except socket.gaierror:
        print("{} This input not valid try again".format(target_user))

txt_fl = open("urvesh.txt", "w")
txt_fl.write("Welcome to the scanner!!\n\n")

start_time = datetime.datetime.now()
print(start_time)

txt_fl.write("Starting time here: {} \n\n".format(str(start_time)[:-3]))


for port in range(1, 1026):

    obj = socket.socket(socket.AF_INET, socket.SOCK_STREAM)
    prt_stts = obj.connect_ex((target_ip, port))
    print("{} : {} Status = {}".format(target_ip, port, prt_stts))
    if prt_stts == 0:

        """print(target_user + ":" + str(port)"""
        txt_fl.write(target_ip + ":" + str(port) + " is open!\n")
end_time = datetime.datetime.now()
print(end_time)

txt_fl.write("\nEnding time here: {} \n".format(str(end_time)[:-3]))

total_time = end_time - start_time
print((total_time))

txt_fl.write("Total time here: {} \n\n".format(str(total_time)[:-3]))

txt_fl.close()
