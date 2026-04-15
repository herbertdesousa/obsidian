Date: 2026-02-03
Tags: [[database]]

You need to prove isolation level

| Isolation level      | Dirty reads   | Lost updates  | Non-repeatable reads | Phantoms      |
| :------------------- | :------------ | :------------ | :------------------- | :------------ |
| **Read Uncommitted** | **may occur** | **may occur** | **may occur**        | **may occur** |
| **Read Committed**   | don't occur   | may occur     | may occur            | **may occur** |
| **Repeatable Read**  | don't occur   | don't occur   | don't occur          | **may occur** |
| **Serializable**     | don't occur   | don't occur   | don't occur          | don't occur   |

At the worst scenario, on serializable, you need to provide a brand new environment for the whole query. The worsted algorithm will write a totally new database to achieve it. But MVCC can help.

MVCC keeps, like Git, a track of the record with it's timestamp, so each snapshot can move on the timeline and isolation level is when the pointer is allowed to moves.