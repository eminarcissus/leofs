# LeoManager's Architecture

LeoManager monitors state of LeoGateway and LeoStorage nodes to keep high availability of your LeoFS. A consistency of RING (*distributed hash table*) of LeoGateway and LeoStorage nodes are always monitored by LeoManager to prevent <a href="https://en.wikipedia.org/wiki/Split-brain" target="_blank">split-brain</a>.


![](../assets/leofs-architecture.007.jpg)

LeoManager manages configurations of a system and information of every node to be able to recover a system reliablely, and the data are replicated by <a href="http://erlang.org/doc/man/mnesia.html" target="_blank">Erlang Mnesia</a> to avoid data loss.

LeoManager provides [leofs-adm as a LeoFS administration commands](../admin/index_of_commands.md) to be able to easily operate LeoFS. The administration commands already cover entire LeoFS features.

## Related Links

- [admin / Index of LeoFS' Command Lines](../admin/index_of_commands.md)
- [admin / settings/ LeoManager Settings](../admin/settings/leo_manager.md)