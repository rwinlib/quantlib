QuantLib 1.12.1

Built with Rtools gcc 4.9.3.

QuantLib headers include on some (header only) boost functionality. So you either need
to add LinkingTo: BH in your R package or provide the boost headers separately.

The lib directory is zipped because the static libs are too large for GitHub.
