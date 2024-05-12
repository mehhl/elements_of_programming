**Lemma 1.3.** A well-formed object is partially formed.

Recall that an object in a partially formed state is an object that can be assigned
to, or destroyed.[^1]

**Assumption 1.** A well-formed object is well-formed with respect of its object type.

**Rationale of assumption.** It's just a nitpick: as defined, objects are or are not
well-formed with respect to the _value type_ of their value. But as EoP states, in 
C++ we can't really talk about non-object types, so it seems natural to just pick
the value type here that is isomorphic to the object type, i.e. represents entities
that are the possible program states of objects of this type.

**Assumption 2.** The well-formed object's type has a non-trivial notion of 
partial-formedness.

**Rationale of assumption.** Otherwise Lemma 1.3  would be meaningless. 
 
**Proof of Lemma.** Take a well-formed object. Since its type has a meaningful
notion of partial-formedness (Assumption 2), the type supports assignment-to and 
destructor procedures. Therefore, any _abstract_ entity representable in the 
associated value type is assignable-to and destructible. (In contrast, a _concrete_ 
entity representable in the associated value type might or might not support these
procedures; it depends on your particular circumstances, and is not subject to 
abstract -- i.e. eternal and unchangeable -- reasoning.) By definition of 
well-formedness, a well-formed object's value represents an abstract entity, and by
Assumption 1, this entity is assignable-to and destructible.

___

[1] One large category of objects that are not partially formed that I
can think of are objects that no longer exist, or haven't been created yet.
Presumably one might need to reason about such objects rigorously, and the notion
might be useful for that.