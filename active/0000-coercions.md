- Start Date: (fill me in with today's date, 2014-08-12)
- RFC PR #: (leave this empty)
- Rust Issue #: (leave this empty)

# Summary

This RFC proposes a tweaked final set of *coercion rules* for Rust 1.0, together
with some new traits and notation for explicit slicing.

Name | From | To | Assumptions
---- | ---- | -- | -----------
Reborrow | `&'a mut T` | `&'b mut T` | `'b <= 'a`


- Reborrow: &'a T -> &'b T, 'b <= 'a
- Reborrow: &'a mut T -> &'b T, 'b <= 'a
- Auto-object: &T -> &Trait /* cannot be abstracted in user-land */
- Forget size: &[T, ..N] -> &[T]


Rust has been gradually changing its *coercion* rules over time,
generally by

# Motivation

Why are we doing this? What use cases does it support? What is the expected outcome?

# Detailed design

This is the bulk of the RFC. Explain the design in enough detail for somebody familiar
with the language to understand, and for somebody familiar with the compiler to implement.
This should get into specifics and corner-cases, and include examples of how the feature is used.

# Drawbacks

Why should we *not* do this?

# Alternatives

What other designs have been considered? What is the impact of not doing this?

# Unresolved questions

What parts of the design are still TBD?
