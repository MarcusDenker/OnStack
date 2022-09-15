Questions:

- Simple replace of method works, but we have to signal the semaphore twice. Why?


- What if the MetaLink adds temps for stack manipulation?
	-> we need to create a new context...

- Blocks. What to do if we install on a node that is part of a block

	-> do we need to replace the compiledBlock of all Closures that are in the system somewhere?
	-> Update the method (or outer block). The compiledBlock is in the literals


Next Step
=========


-> Try to not replace the method, but create a new context and insert that intead of the
orginal.
	-> take care about temps
	-> and the operand stack... 
			can this lead to problems? e.g. link is executing when receiver is already pushed on the stack. e.g. debugger

-> Try to replace a method where we have to change the PC, too.
	- How to know the size of the BC that the metalink creates?

-> How do we query when installing a link if that method is on the stack?



Notes:
======



Later:

- Check Restart in the Debugger? How is it implemented? It does do replace a context!
	--> this is I think preRefresh:, so not that interesting.
- Experiment in debugger: can we now use breakpoints as people think, that is, add a br later and 
   debugger will break if we continue.
- Recursive methods?
- What is the API for on-stack replacement?
- Think about refactorings in general, can we support more?
