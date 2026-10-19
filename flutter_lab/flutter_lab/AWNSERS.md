What is the difference between what runApp receives and what 
MaterialApp receives as home?

ans) runApp() receives the root widget of the entire Flutter application and attaches the widget tree to its rendering engine.MaterialApp's home receives the default screen/page widget (in this case, HomePage) that is rendered as the main root route of the application layout. 

Why are the fields of a StatelessWidget final? What would the 
compiler say if you removed final? 
ans) The fields of a StatelessWidget must be final as stateless widgets are fixed. If you remove final, there will be an error “Instance fields of stateless widgets should be final” because mutable state inside a stateless widget violates the architectural constraints of flutter's rendering pipeline

 Draw the widget tree of your screen on paper, from LabApp down 
to the three Text widgets. How many levels deep is the Text('Max: ..')? 
ans) 7 Levels

Why does GoalBanner not need setState? What would you have to do to make it show a new count?
ans) GoalBanner doesn't need setState because it's just a StatelessWidget that displays whatever data is handed to it. If you want it to show a new count, a parent widget has to rebuild and pass down a completely new count value to it.