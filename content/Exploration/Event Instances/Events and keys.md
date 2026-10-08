See also [[Keys]]

- Events don't have a natural set of properties that together ensure their uniqueness
	- Timestamp + activity is not sufficient to ensure an event is unique
	- Timestamp + activity + object id similarly is not sufficient as a single event might act on multiple objects
- So, having an identifier could be useful for events constraint events, to refer to events and also to identify events --> this is the purpose of an identifier (the key)
	- However, the identifier is artificially created and does not on its own already guarantee uniqueness and uniqueness must be checked/modelled

- Source data generally does not provide event identifiers, (e.g. case studies NXP and Croma)  
    --> so the assumption of event identifiers does not hold in general, and hence we must deal with the assumption that it is generally not there.
- If there is no explicit event identifiers we might have
	- convergence/duplicate events --> deduplication
	- lower level of granularity than desired events --> event abstraction
- Therefore, we must deal with **event resolution**.
	- Similarly to objects and relationships, events need to be modelled (resolved) in OCED and EKG.