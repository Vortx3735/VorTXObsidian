The arm uses an encoder ( values are in terms how far the encoder is rotated) to get values so that the once it hits a the set limit which is a soft limit so that the arm does not go too far back when it goes up. When it goes down it hits a soft limit which after it hit s the limit it uses gravity to go down slowly. 
 Example of the code of arm going down using  brakes and gravity : 
``` public BooleanSupplier getArmDown() {

return () -> position <= (Constants.ArmConstants.groundArmPos + .05);

}

public void setArmBrake(IdleMode mode) {

ArmNeo1.setIdleMode(mode);

ArmNeo2.setIdleMode(mode);

}
```
Example  of moving to set point using the positioning from the encoder to  know where to go : 

```
```public void moveToSetpoint(double setPointPos, double p) {

move((setPointPos - getArmPos()) * p);

}

  

public void hold() {

// double pos = armEncoder.getAbsolutePosition();

setpoint = (int)position;

ArmNeo1.set(hold.calculate(position * 2 * Math.PI, setpoint * 2 * Math.PI) + armFF.calculate(position * 2 * Math.PI, kv));

}
Arm getting values from the encoder :
public double getRadiansTravelled() {

return armEncoder.getDistance()/(2*Math.PI);

}
```


 