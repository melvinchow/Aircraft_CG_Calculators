# Aircraft_CG_Calculators
Calculators for determining optimal Center of Gravity positions on aircraft

While I was reading about and building model aircraft, I noticed many Center of Gravity recommendations from the manufacturer are either missing, incorrect, or not ideal for the style of flying I would like to do with my models.

So I made a set of calculators that use length and angle measurements taken from models in order to calculate this, with all the complex math handled automatically on the pages.

There are three versions so far, based on the kind of aircraft design in question.

The calculators assume that most CG recommendations are based on % MAC (Mean Aerodynamic Chord) measurements.  Most maiden flights are recommended to be performed with a CG at 25% MAC.  WWII Warbirds might prefer to be nose-heavier at 22% to 24% MAC.  The pilot can gradually move the CG tail heavier (up to 33% MAC) if more slow-speed acrobatic flying is desired.  A CG between 33% to 40% MAC is possible for the most extreme acrobatic performance, but a sophisticated, well-programmed gyro is highly recommended, or else the plane might not stay afloat.

## 1) MAC CG Sweep Wing

For the conventional main wing + tailplanes layout (ex: Cessna 172, Piper Cherokee, F86 Sabre).  Accounts for wing sweep, if any.

Tailplane measurements are not used here (but I may implement this in an update), but in general, if the tail control surfaces are large (ex, Edge 540), then the plane can fly at tail-heavy CGs.

## 2) MAC CG Cranked Wing

Same as the first version, except this includes more complex math to account for wings with abnormal shapes, whether it be an elliptical wing (ex: Supermarine Spitfire) or a wing with changing shapes along its span (ex: F15 Eagle, B2 Spirit), the wing would be divided into sections, measured per section, then combined together to compute an average.  In the rare occasion the plane has multiple sweep angles (ex: F16XL), the average angle is chosen.

If the wing design looks close enough to a conventional wing, one can always lay a ruler along the trailing edge, pretend the wing is not cranked, and compute an estimate using the conventional calculator.  You'll get close enough to the real optimal CG this way, and your preferred CG will be discovered through test flights anyways.

## 3) MAC CG Delta Canard

This configuration is the most complex to tackle, because Delta Canards take advantage of vortex lift from high AOAs (Angles of Attack) that conventional wing configurations never see.  It also needs to account for lift from the canards.  So this is tackled in 3 stages:

a) Linear Estimate
- The most basic CG estimate based on aircraft wing measurements ; assumes zero AOA flight

b) AOA
- The Center of Pressure (and hence optimal CG) moves rearward with more AOA due to the introduction of vortex lift.  Given that every delta wing is designed different, wind tunnel testing would give a more accurate change in performance than a calculator, so results should be taken with a grain of salt.

c) Wing Loading
- Delta Wings are unique from conventional wings, in that ideal CG changes with wing loading.  As wing loading gets heavier, optimal CGs move aft as well.  This section attempts to estimate this change given parts A and B.  But this is also a VERY rough estimate and results should be taken with a grain of salt.

# How to use:
Download the HTML  
Open in any web browser  
Input measurements and see the results
