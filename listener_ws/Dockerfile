FROM ros:foxy

# Change the default shell to Bash
SHELL [ "/bin/bash" , "-c" ]

RUN mkdir work_space
WORKDIR work_space

COPY . .
RUN chmod +x launch.sh
RUN colcon build --packages-select py_sub

CMD ["./launch.sh"]
