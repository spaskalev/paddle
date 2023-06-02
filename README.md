# Paddle

Paddle is a design experiment in a chorded keyboard using only two keys. The goal for it is to have an accessible and time-insenstive input system. A user that could operate only a single switch at time should still be able to use paddle to input data.

Radio operators can encode data using a single key by using the relative length between keying to distinguish between dits and dahs. To make an input system that is not based on time a second key is added. Starting from the state of (0,0) and finishing at the same state the series of key transitions can be used to encode input.

# Transition states

As paddle should be usable by toggling only one key at a given moment the following is a table of the allowed state transions using two keys.

```
(0,0) -> (0,1)
(0,0) -> (1,0)
(1,0) -> (0,0)
(1,0) -> (1,1)
(0,1) -> (1,1)
(0,1) -> (0,0)
(1,1) -> (0,1)
(1,1) -> (1,0)
```

The following state transitions are not allowed and must be rejected by paddle.

```
(0,0) -> (1,1)
(0,1) -> (1,0)
(1,0) -> (0,1)
(1,1) -> (0,0)
```

# Encoding

A paddle sequence consists of the following four operations - "A Down", "A Up", "B Down", "B Up" where "A" and "B" are the two keys. They can be shortened to "a", "A", "b" and "B".
