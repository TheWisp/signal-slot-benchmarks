
# MSVC (Windows)

**_Higher score is better._** _N / (sample size / count)._

### Performance of Thread Safe Libraries

| Library | construct | destruct | connect | emission | combined | threaded | total |
|---------|-----------|----------|---------|----------|----------|----------|-------|
| * fr00b0 nod | 66851 | 8444 | 6803 | 44891 | 3809 | 260 | 131057 |
| * Pal Sigslot | 66239 | 7762 | 5832 | 43143 | 3373 | 231 | 126580 |
| * nano-signal-slot v2x | 67798 | 4792 | 3785 | 46320 | 2143 | 174 | 125011 |
| * cpp11nullptr lsignal | 50272 | 3907 | 2162 | 43228 | 1388 | 131 | 101088 |
| * Kosta signals-cpp | 72334 | 5955 | 1348 | 13416 | 964 | 1 | 94017 |
| * Montellese cpp-signal | 29258 | 5401 | 5111 | 43680 | 2609 | 199 | 86258 |
| * winglot Signals | 10515 | 3698 | 3771 | 44146 | 1688 | 165 | 63983 |
| * Boost Signals2 | 7931 | 2938 | 2136 | 10564 | 986 | 1 | 24556 |
| * neolib signal | 5764 | 2854 | 2668 | 9567 | 1026 | 127 | 22005 |

### Performance of Thread Unsafe Libraries

| Library | construct | destruct | connect | emission | combined | threaded | total |
|---------|-----------|----------|---------|----------|----------|----------|-------|
| jeffomatic jl_signal | 54956 | 15982 | 38908 | 49249 | 11795 | 0 | 170891 |
| Wink-Signals | 75446 | 11487 | 8938 | 49565 | 5197 | 0 | 150633 |
| Montellese cpp-signal | 75224 | 10157 | 8140 | 50076 | 4734 | 0 | 148331 |
| SimpleSignal | 75867 | 9440 | 7937 | 47752 | 4501 | 0 | 145497 |
| Yassi | 75001 | 8438 | 6523 | 50471 | 3873 | 0 | 144306 |
| Pal Sigslot | 72531 | 8148 | 7872 | 47843 | 4160 | 0 | 140555 |
| nano-signal-slot v2x | 72763 | 6388 | 4294 | 49396 | 2754 | 0 | 135596 |
| nano-signal-slot v1x | 59363 | 11064 | 8666 | 49153 | 5069 | 0 | 133314 |
| amc522 Signal11 | 66104 | 7677 | 5515 | 47584 | 3344 | 0 | 130224 |
| mwthinker Signal | 64006 | 7244 | 5721 | 49513 | 3299 | 0 | 129783 |
| vdksoft signals | 65324 | 5749 | 5875 | 49108 | 3185 | 0 | 129241 |
| joanrieu signal11 | 55865 | 9655 | 7699 | 44064 | 4306 | 0 | 121589 |
| pbhogan Signals | 54437 | 6816 | 5950 | 41798 | 3362 | 0 | 112363 |
| EvilTwin Observer | 65633 | 4255 | 2435 | 20482 | 1467 | 0 | 94271 |
| supergrover sigslot | 12323 | 2122 | 2708 | 49523 | 1123 | 0 | 67799 |
| Boost Signals | 9350 | 3295 | 1194 | 15290 | 769 | 0 | 29898 |
| neolib signal | 6335 | 4787 | 3828 | 12619 | 1508 | 0 | 29078 |

___
_Size results are the size of object files from release build with Visual Studio 17._

### Metrics of Thread Safe Libraries

| Library | Build Size | Header Only | Data Structure | Thread Safe |
| ------- |:----------:|:-----------:| -------------- |:-----------:|
| [* Pal Sigslot](https://github.com/palacaze/sigslot) | 840 kb | X | singly linked list | X |
| [* Montellese cpp-signal](https://github.com/Montellese/cpp-signal) | 843 kb | X | std::forward_list | X |
| [* nano-signal-slot v2x](https://github.com/NoAvailableAlias/nano-signal-slot/tree/rework) | 852 kb | X | std::forward_list | X |
| [* winglot Signals](https://github.com/winglot/Signals) | 869 kb | - | **std::list | X |
| [* fr00b0 nod](https://github.com/fr00b0/nod) | 919 kb | X | std::vector | X |
| [* Kosta signals-cpp](https://github.com/Kosta-Github/signals-cpp) | 925 kb | X | std::vector | X |
| [* cpp11nullptr lsignal](https://github.com/cpp11nullptr/lsignal) | 1035 kb | X | **std::list | X |
| [* neolib signal](https://github.com/i42output/neolib) | 1288 kb | X | **std::unordered_map | X |
| [* Boost Signals2](http://www.boost.org/doc/libs/1_58_0/doc/html/signals2.html) | 2604 kb | - | ? | X |

### Metrics of Thread Unsafe Libraries

| Library | Build Size | Header Only | Data Structure | Thread Safe |
| ------- |:----------:|:-----------:| -------------- |:-----------:|
| [nano-signal-slot v1x](https://github.com/NoAvailableAlias/nano-signal-slot) | 164 kb | X | singly linked list | - |
| [jeffomatic jl_signal](https://github.com/jeffomatic/jl_signal) | 179 kb | - | doubly linked list | - |
| [Wink-Signals](https://github.com/miguelmartin75/Wink-Signals) | 205 kb | X | std::vector | - |
| [vdksoft signals](https://github.com/vdksoft/signals) | 209 kb | - | singly linked list | * |
| [Montellese cpp-signal](https://github.com/Montellese/cpp-signal) | 212 kb | X | std::forward_list | - |
| [Pal Sigslot](https://github.com/palacaze/sigslot) | 222 kb | X | singly linked list | - |
| [nano-signal-slot v2x](https://github.com/NoAvailableAlias/nano-signal-slot/tree/rework) | 229 kb | X | std::forward_list | - |
| [SimpleSignal](https://github.com/larspensjo/SimpleSignal) | 235 kb | X | std::vector | - |
| [supergrover sigslot](https://github.com/supergrover/sigslot) | 244 kb | - | std::list | - |
| [mwthinker Signal](https://github.com/mwthinker/Signal) | 247 kb | - | std::list | - |
| [joanrieu signal11](https://github.com/joanrieu/signal11) | 274 kb | X | std::list | - |
| [Yassi](http://www.codeproject.com/Articles/867044/Yassi-Yet-Another-Signal-Slot-Implementation) | 274 kb | X | std::vector | - |
| [amc522 Signal11](https://github.com/amc522/Signal11) | 275 kb | X | std::vector | - |
| [EvilTwin Observer](http://eviltwingames.com/blog/the-observer-pattern-revisited/) | 282 kb | X | std::vector | - |
| [pbhogan Signals](https://github.com/pbhogan/Signals) | 286 kb | X | std::set | - |
| [Boost Signals](http://www.boost.org/doc/libs/1_56_0/doc/html/signals.html) | 455 kb | - | ? | - |
| [neolib signal](https://github.com/i42output/neolib) | 644 kb | X | **std::unordered_map | - |

_* Library is thread safe._
<br/>
_** Uses additional data structures._

Benchmark Algorithms
--------------------

_The individual benchmark algorithms are completely generic through templates._

| Algorithm | Description |
| --------- | ----------- |
| [validation_assert](https://github.com/NoAvailableAlias/signal-slot-benchmarks/blob/master/benchmark.hpp#L21) | Make sure each signal implementation is functioning correctly. |
| [construction](https://github.com/NoAvailableAlias/signal-slot-benchmarks/blob/master/benchmark.hpp#L50) | Time the construction of a Signal to an N number of Foo instances. |
| [destruction](https://github.com/NoAvailableAlias/signal-slot-benchmarks/blob/master/benchmark.hpp#L71) | Time the destruction of a Signal and associated Connections to N number of Foo instances. |
| [connection](https://github.com/NoAvailableAlias/signal-slot-benchmarks/blob/master/benchmark.hpp#L101) | Time Signal connections to a randomized N number of Foo instances. |
| [emission](https://github.com/NoAvailableAlias/signal-slot-benchmarks/blob/master/benchmark.hpp#L129) | Time the duration of an N slot emission. |
| [combined](https://github.com/NoAvailableAlias/signal-slot-benchmarks/blob/master/benchmark.hpp#L159) | Time construction, destruction, connection, and emission together. |
| [threaded](https://github.com/NoAvailableAlias/signal-slot-benchmarks/blob/master/benchmark.hpp#L186) | Same as the "combined" test except threaded using a shared Signal. |
<br/>