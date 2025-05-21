# VorTX command structure

In VorTX we use command-based programming to run our robot. Commands are basically segments of code that allow the robot to do different tasks. For example, moving an elevator to a set position could be a command. Read up about this here: https://docs.wpilib.org/en/stable/docs/software/commandbased/commands.html

One of the big problems we encounter while programming is where to put these commands. Do they get their own file? Or are they defined in each subsystem? Or do we use a runcommand/instantcommand to run a method directly? This guide will answer those questions.