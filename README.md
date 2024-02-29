# Задача 0

Согласно теореме CAP к какой части вы можете отнести СУБД:

* DragonFly
* ScyllaDB
* ArenaDataDB


##  Решение

* DragonFly - обеспечивает eventual consistency => AP система
* ScyllaDB - согласно документации consistency_level можно настраивать. Если сделать его равным ONE и выставить replica_factor для записи равным N, то получится AP гарантия(координатор дождется лишь один ответ, остальное может записаться позже ответа клиенту). Если же сделать consistency_level = QUORUM, то получится нечто похожее на CP, ибо на каждую операцию чтения/записи будет требоваться ответ большинства узлов, что не переживает split brain. Но судя по [документации](https://opensource.docs.scylladb.com/stable/architecture/architecture-fault-tolerance) ScyllaDB подается как AP система, нежели CP
* ArenaDataDB - ближе всего к CP системе, однако информации слишком мало





