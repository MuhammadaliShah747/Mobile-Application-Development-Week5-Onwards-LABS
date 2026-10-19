What is the difference between what runApp receives and what 
MaterialApp receives as home?

ans) runApp() receives the root widget of the entire Flutter application and attaches the widget tree to its rendering engine.MaterialApp's home receives the default screen/page widget (in this case, HomePage) that is rendered as the main root route of the application layout. 

Why are the fields of a StatelessWidget final? What would the 
compiler say if you removed final? 
ans) The fields of a StatelessWidget must be final as stateless widgets are fixed. If you remove final, there will be an error “Instance fields of stateless widgets should be final” because mutable state inside a stateless widget violates the architectural constraints of flutter's rendering pipeline