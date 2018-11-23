QuantLib 1.14
Boost 1_68_0

Built with Rtools35, gcc 4.9.3.

QuantLib headers include on some (header only) boost functionality. So you either need
to add LinkingTo: BH in your R package or provide the boost headers separately.

The lib directory is zipped because the static libs are too large for GitHub.
