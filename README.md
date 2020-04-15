# IOCP_Xplane
This IOCP class allow to exchange data with X-plane and flight simulator over network via UIPCX plugin, openCockpit IOcards use the same protocol to communicate with the simulator.

This class is to use with Python 3
Use:
import Iocp

iocp = Iocp()
iocp.connect(("ip of xplane", port_to_connect)  -> return 0 if ok or -1
iocp.refister(data)  where data is a list of integer correlate to uipcxdatos file in plugin directory of x plane
                      and return a dict{} with the var number as key and the value
iocp.recvData()  check if new values is arrived and return them in a dict{} or -1
iocp.sendData(val,var)  send data to server val and var must be str ("501","2550")
iocp.close()  send 'Fin' to the server and close the socket

The class work fine to receive data in non bloxking mode, i use it in a program to remotly control analog instrument for my pit.

