## Instructions to Use the Docker Image

1. **Pull the Docker Image:**

    Run the following command to pull the image:
    ```bash
    docker pull soumitramaxx/cs378-lab3:latest
    ```

2. **Allow Access to X Server:**

    On your local machine, run this command to allow Docker containers to connect to your X server:
    ```bash
    xhost +local:root
    ```

3. **Start PulseAudio:**

    Ensure that PulseAudio is running on your local machine by executing:
    ```bash
    pulseaudio --start
    ```

4. **Run the Docker Container:**

    Use this command to start the Docker container with the necessary audio and display settings:
    ```bash
    docker run -it \
        --device /dev/snd \
        -v /run/user/$(id -u)/pulse:/run/user/$(id -u)/pulse \
        -v /dev/shm:/dev/shm \
        -e PULSE_SERVER=unix:/run/user/$(id -u)/pulse/native \
        --group-add $(getent group audio | cut -d: -f3) \
        -e DISPLAY=$DISPLAY \
        -v /tmp/.X11-unix:/tmp/.X11-unix \
        soumitramaxx/cs378-lab3
    ```

5. **Navigate to the Code Directory:**

    Once inside the container, navigate to the directory where the code is located:
    ```bash
    cd /home/soumitra/Downloads/lab3
    ```

6. **Modify `messages.txt`:**

    Edit the `messages.txt` file to include the messages you want to send.

7. **Run the Code:**

    Finally, execute the Python script using:
    ```bash
    python3 run.py
    ```

