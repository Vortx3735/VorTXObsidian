Initializing subsystems like the arm, shooter, intake, etc. with the IDs of the motors. Initializing the command file takes in a parameter of the subsystem which you are creating a command file for. This should all be initialized BEFORE the constructor. 
```Ex:
public static Intake intake = new Intake(16);
public static IntakeCom intakecom = new IntakeCom(intake);
```

Inside the constructor is the button bindings. At the top of the constructor, initialize the VorTX controller library with this call.
`configureBindings();`

Once this has been done, you can create functions utilizing values from the VorTX controller library.

Uses button bindings that are available from the VorTX Xbox controller library. These are the options for buttons.
```
aButton, bButton, xButton, yButton, view, menu, ls, rs, lb, rb, lt, rt,
povUp, povUpRight, povRight, povDownRight, povDown, povDownLeft, povLeft, povUpLeft
```

Put the command / subsystem to use for the button binding inside a function. 
```Ex:
con2.xButton.whileTrue(

	intakecom.intakeNoteCom()

);
```

A run command is a way to run a command for a certain subsystem. Usually, these run commands are placed within a button binding which can be seen above. Inside the run command, the first argument is the command you want to run. This can be done with the double semicolons below, or can be done with a lambda.

```Ex:
intake::stopIntake        || (Runs the command stopIntake)
() -> intake.StopIntake() || (Also runs the command stop Intake)
```

Example of run commands 
```Ex:
intake.setDefaultCommand(
	new RunCommand(
		intake::stopIntake,
		intake
	)
);
```