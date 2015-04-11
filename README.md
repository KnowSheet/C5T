## Current Components

The componets of **Current**, somewhat user-facing in the top to implementation details below.

Task | Stack | Module | Maturity Level | Remaining Milestones / Comments
:--: | :---: | :----: | :------------: | :-----------------------------:
Language bindings | Developer-facing | Not started
Browser-based data dictionary creation | Developer-facing | Not started
Browser-based topology definition | Developer-facing | Not started
Large Android and iPhone clients | Frontend | [Alohalytics](https://github.com/KnowSheet/Alohalytics) | Used in Maps.me | Diverged between Maps.me and KnowSheet. Need to converge. (*)
Data Dictionary Thesaurus | FE + BE | Originally [Bricks/cerealize](https://github.com/KnowSheet/Bricks#cerealize) + need to rethink iOS | Mature + In progress | Dima has the design, Dima to code over the weekend.
iPhone Mixpanel client replacement | iPhone | In progress | In progress | Dima + Sirewire = `<3`.
Web Client | Web | - | - | Uncertain whether it's required for V1 given how well we support POST-ing data into Bricks / Sherlock. Have business need very soon though.
Server-side data aggregation | Backend | Alpha in [SimpleServer](https://github.com/KnowSheet/SimpleServer) | In progress | Dima + Sirewire = `<3`. Befriend with iOS-friendly data dictionary definition.
TailProduce: Multiple-stream-based data crunching and serving | Backend | - | Have an old design doc. | Design polished several times. Dima has good vision. Implementation will start once we close the loop and onboard several customers.
Stream-based data crunching and serving | Backend | Part of [Sherlock](https://github.com/KnowSheet/Sherlock) | Close to V1 | Ready to launch workers on per-stream basis, waiting for `TailProduce` for multi-stream joins to become as easy to implement.
Key-Value Storage over stream-centric storage | Backend | Part of [Sherlock](https://github.com/KnowSheet/Sherlock) | DesignDoc + Pilot Implementation Ready | Support polymorphic types. Add consistency policies. Add CRUD+REST.
Append-only stream-centric storage | Backend | [Sherlock](https://github.com/KnowSheet/Sherlock) | Close to V1 | Persistence layer still on my plate -- [@dkorolev](github.com/dkorolev)
Browser-level dashboard | FE + BE | [KnowSheet/Web](https://github.com/KnowSheet/Web) | Serves TailProduce demo. | Need to rename into `Dashboard`. Uncertain whether it is launchable w/o WebSockets due to large memory footprint in Firefox.
Model optimizer | Backend | [FNCAS](https://github.com/KnowSheet/fncas) | Ready to launch | Compile gradients, not only input functions.
REPL shell for Bricks | Backend | [Bricks/KnowSheet-REPL](https://github.com/KnowSheet/KnowSheet-REPL) | Ready to launch
Backend-grade visualization | Backend | [Bricks/graph](https://github.com/KnowSheet/Bricks#visualization-library) | V1 launched
In-memory message queue | Backend | [Bricks/mq/inmemory](https://github.com/KnowSheet/Bricks/tree/master/mq/inmemory) | Ready to launch | Policy to drop vs. wait on overflow.
JSON and binary serialization | Backend | [Bricks/cerealize](https://github.com/KnowSheet/Bricks#cerealize) | V1 launched
HTTP Client | Backend | [Bricks/net](https://github.com/KnowSheet/Bricks#http-client) | V1 launched
HTTP Server | Backend | [Bricks/net](https://github.com/KnowSheet/Bricks#http-server) | V1 launched

(*) Need to a) evaluate the need in FileSystem-based storage for most users (in-memory vs. persistent log entries in case of offline), b) evaluate the need in Android coming launching in V1, c) Move back to `Bricks+Sherlock` wrt storage / network layer.

## Current Priorities

In rough order, to be completed by 4/19:

* iPhone Mixpanel [somewhat] drop-in replacement.
* Data dictionary thesaurus definition for iPhone + backend.
* Key-Value storage on the backend.
* Consistency policies for Key-Value storage on the backend.
* Data stream persistence ( + overflow policy for in-memory message queue).
* Data stream replication.
* Key-Value storage REST API (for CTFO & new demo).
* Proto-implementation of TailProduce logic (on one stream, but worker-based instead of listener-based).
