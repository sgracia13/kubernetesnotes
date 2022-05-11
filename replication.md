- There needs to be a way for you to
check if a container is still alive.
- This is done through liveness probes.
- There are 3 different methods/mechanisms 
of getting this done:
1. HTTP GET --> if probe gets 200 or 300 
response, probe is successful, if 
probe receives error 4xx then it fails
and a restart ensues.
2. TCP Socket --> attempts to open 
tcp connection, if connection is established
successfully, probe is successful. If not it fails
and the container restarts.
3. Exec Probe --> executes an arbitrary command,
inside container and checks exit status code.
If the status code is 0, the probe is successful. 
All other codes are considered failures.


