# MultidexProguardFail
example project of proguard panic during multidex


#Project specifics:

3 modules, 2 libs and 1 app

libs have flavors

app has flavors & dimensions

gradle 2.0.0-alpha6

android studio 2 - alpha 7
 
 <b>Libs added:<b/>
 
retrolambda
 
dagger2
 
retrofit
 
JDK8 used
 
 
#Execute:
gradlew clean :mylibrary1:lint :mylibrary2:lint assemble :app:connectedGoldCustomerADebugAndroidTest

<b>Note the proguard removes all android inner classes, and retrofit even tough they were properly defined in proguard rules.pro.</b>

Attempt to work around this was in app build gradle file by defining 

  multiDexKeepProguard file('proguard-rules.pro') <-- project rules
  
  multiDexKeepProguard file('proguard-rules-multidex.pro') <-- project rules + default android proguard  rules


