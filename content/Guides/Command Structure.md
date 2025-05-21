# VorTX command structure

In VorTX we use command-based programming to run our robot. Commands are basically segments of code that allow the robot to do different tasks. For example, moving an elevator to a set position could be a command. 
Read up about this here: https://docs.wpilib.org/en/stable/docs/software/commandbased/commands.html

## base commands
These commands that only use 1 subsystem. For example, move elevator to level 2. Put these commands directly into their respective subsystems.

## multi-subsystem commands
These are commands that use base commands from different subsystems. For example, score on level two of the reef. Put these in the command factory file and group them together using either parallel command or sequential command group.

## complex commands
These are commands that require more intricate logic. For example, auto-align to an apriltag. Put these in their own file and override the initialize/execute/interrupted/end fields with your code.