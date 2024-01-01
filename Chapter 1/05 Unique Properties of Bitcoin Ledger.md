The beauty of a Bitcoin ledger and protocol is that it is one system, but it can be used as many different things depending on how you see it and use it. It can be abstracted as a Database, a Turing Tape, Accounting book, system log etc. All of these abstractions allow for using the network and ledger to build systems that need such abstractions. Let us look at some of these abstractions.

Infinite Database: Bitcoin ledger used for storing data can be used infinitely as long as you pay the small one-time network fee for the transactions. If not the nodes who participate in the network, there will be specialised nodes in future who work as archiving nodes for the data stored and provide the data retention services. This means that the APIs that you build can work indefinitely till the bitcoin network is functional in a way enabling the creation of infinite APIs. In a later chapter we will talk about the Planaria framework which works as a RAM accessing this infinite database (bitcoin) on a real time basis and updating every event filtered by application specified criteria. One huge benefit of bitcoin over other databases is that the data stored is never corrupted (distributed network keeps multiple copies), if you mess up and lose records, you can always rewind and recreate the database, so it also provides excellent failsafe measures.

Infinite universal spreadsheet: This is another way of looking at the universal public Bitcoin Ledger. Since everything recorded is a transaction between two parties, it is kind of a distributed global spreadsheet available to anyone who is willing to pay the tiny amount of fee to update it and has a window to view a subset or whole of it. It can also be thought of a global accounting book.

Infinite Motor: If you see, Bitcoin is cyclic. It has an approximately 10 minutes cycle which the network keeps repeating. But each cycle is unique in its own way and its content which is made up of a selective history of the human interactions that are selected and logged into Bitcoin. It’s this property if we think further, we can think of Bitcoin as a perpetual rotating machine, an infinity motor, which (based on its algorithm) is capturing transactions by navigating in time and producing them as events.

<img src="./assets/BSVAcad-Dev_Chapter1-Image10a.gif"/>

This "motor" travels through time and collects all the events (transactions) that happen through each rotation and takes an immutable snapshot (a block). The rotation logic (Bitcoin's algorithm) is deterministic and secure (powered by Proof of Work), making it the perfectly stable piece of technology to power all kinds of useful machines.

So now that we have established an abstraction, Bitcoin == Motor

We can then think about how to build a machine with a motor (Bitcoin). But first, what exactly is a "machine"?

A machine is a function. A machine takes the motor as the constant source of energy and transforms the energy into various forms that can be consumed by humans or other machines.

Machine = F(Motor): You can create an infinite number of "machines" from a single reliable motor, which is Bitcoin.

<img src="./assets/BSVAcad-Dev_Chapter1-Image10b.gif"/>

This abstraction in turn can enable building Finite state machines and infinite state Machines on Bitcoin.

State machines are quite extensively used in designing real life applications and are a mathematical model of computation which exist in a specific state at any given point in time. When the conditions or external input is changed, the state machines go from one state to another. Simple examples in real life are vending machines which dispense products when a certain number of coins are inserted or elevators which start moving when you step on the first step. State machine diagrams are widely used when designing software applications to create logical flow of defining rules of application behaviour using UML diagrams or such.

State machines can be finite state machines (FSM) or infinite state machines depending on the design of the machine. Typically, most of the real-world applications are designed as FSM as they are in exactly one finite state at any given time. Figure below shows a generic state machine and the flow of various interactions between components. It is possible to build this complete system using bitcoin which we will see in later chapters.

<img src="./assets/BSVAcad-Dev_Chapter1-Image11-updated 1.jpg"/>
<h3 align = "center">A generic state machine and its components</h3>

Input: an event listener that listens to real time events/states from bitcoin

Transition logic: Program that will handle the state change using CRUD operations API

State Memory: A memory to persist the state attributes and updates

Output Logic: An event producer that publishes custom programmable events for other modules and SSE

A traffic light system can be taken as an example of an FSM. It contains three light bulbs which are red-green-yellow based on the current state and each state is dependent on the last state and follows a strict sequence of state change done by the event or input of the time clock.

These state machines are heavily used in the world of Internet of things and using bitcoin based operating system which require minimal computing it is possible to build such machines.

Infinite Tape: In computer science and computational theory, the idea of Turing machine and Turing completeness of machine is considered quite an important measure to attribute the capabilities of a certain machine. Turing in 1930 created an abstract model for a machine, hypothetical it may be, but can simulate any computer algorithm no matter how complex it is.

As Turing wrote in The Undecidable, p. 128:

It is possible to invent a single machine which can be used to compute any computable sequence. If this machine U is supplied with the tape on the beginning of which is written the string of quintuples separated by semicolons of some computing machine M, then U will compute the same sequence as M.

A graphic representation of such machine is shown below:

<img src="./assets/BSVAcad-Dev_Chapter1-Image11-updated 2.jpg"/>

It consists of an infinitely long tape which acts as the memory in a typical computer, a head which can be positioned on the individual square which can read and write on the tape, one at a time (during Turing’s time, the head was imagined as a typewriter). The typewriter writes 1 or 0 on the tape one at a time and the same is for reading, which happens one at a time. The typewriter is programmed to perform the next step based on its current state and the inputs that it reads from the tape.

Turing machines were the first general purpose model of a computer and a Universal Turing machine is conceptualised as a Turing machine which can simulate any computers of past, present and future hence having the capability to solve any computer algorithm.

Extending it to computation, The Church-Turing thesis later proposed that any real-world computation can be translated into an equivalent computation involving a Turing machine. Typically, in a real-world scenario, this computation requires recursive functions. Languages which allow for recursive functions by looping are considered as having capability to perform any computation making them Turing complete but suffer from the well-known unresolved issue of halting problem. Halting problem is the problem of determining, from a description of an arbitrary computer program and an input, whether the program will finish running, or continue to run forever.

Bitcoin does solve this issue quite elegantly, by breaking the system into two parts, One is the Tape and the program managing that tape. If we take the abstraction of Bitcoin as a Tape, it comes with the following properties of the “Tape”.

The tape moves one direction: forward.
Tape is for keeping track of work accomplished.
Work may happen on-tape or off-tape.
Work is publicly published, which allows anyone to easily verify the work themselves.
Work can write back to the tape, but this is optional.
By looking at Bitcoin as a never-ending tape that grows every ten minute or so, we can even view Bitcoin as a form of "tape".

Second part is the bitcoin network which acts as the typewriter in the Turing machine. Bitcoin Script language allows for simple recursion using the method to unroll the loops in computation by its property of having two stacks. The Bitcoin scripting language is a stack-based language similar to Forth. There are two stacks known as the main stack and the alt stack. Script commands, known as ‘OP_CODEs’ operate on the values in the main stack, while the alt stack is used as an additional store of data.

The language was deliberately designed to exclude looping constructs to avoid the possibility of DOS attacks, however the language has many features including commands to access and manage values within the main stack (for example, OP_PICK and OP_ROLL). The predicate logic system deployed in Bitcoin as a scripting language is equivalent to Wolfram’s (2,3) Turing Machine. With this insight, we see that Bitcoin is functionally a system that is known as a Total Turing Machine. The complete proof of this is out of scope of this course but the paper mentioned below is available for interested readers to explore further on how to create recursive computation using unrolling of loops in Bitcoin Script.

Bitcoin: A Total Turing Machine by Craig S. Wright https://link.springer.com/chapter/10.1007/978-3-030-29516-5_18

This property is extremely important and useful in building Turing complete machines using bitcoin at the back as a tape. In fact, this system enables creation of Oracles and Oracle Turing machines which have the need of infinite tape to function. These use cases will be out of scope for this course or chapter, but the idea here is to give you all a preview of what are the capabilities of this Bitcoin system and what are the possible use cases that can be built using this system.
