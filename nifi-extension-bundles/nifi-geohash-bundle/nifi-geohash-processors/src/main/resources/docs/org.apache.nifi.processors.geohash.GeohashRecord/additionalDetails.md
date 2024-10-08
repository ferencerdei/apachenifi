<!--
  Licensed to the Apache Software Foundation (ASF) under one or more
  contributor license agreements.  See the NOTICE file distributed with
  this work for additional information regarding copyright ownership.
  The ASF licenses this file to You under the Apache License, Version 2.0
  (the "License"); you may not use this file except in compliance with
  the License.  You may obtain a copy of the License at
      http://www.apache.org/licenses/LICENSE-2.0
  Unless required by applicable law or agreed to in writing, software
  distributed under the License is distributed on an "AS IS" BASIS,
  WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
  See the License for the specific language governing permissions and
  limitations under the License.
-->

# GeohashRecord

## Overview

A Geohash value corresponds to a specific area with pre-defined granularity and is widely used in identifying,
representing and indexing geospatial objects. This GeohashRecord processor provides the ability to encode and decode
Geohashes with desired format and precision.

### Formats supported

* BASE32: The most commonly used alphanumeric version. It is compact and more human-readable by discarding some letters
  (such as "a" and "o", "i" and "l") that might cause confusion.
* BINARY: This format is generated by directly interleaving latitude and longitude binary strings. The even bits in the
  binary strings correspond to the longitude, while the odd digits correspond to the latitude.
* LONG: Although this 64-bit number format is not human-readable, it can be calculated very fast and is more efficient.

### Precision supported

In **ENCODE** mode, users specify the desired precision level, which should be an integer number between 1 and 12. A
greater level will generate a longer Geohash with higher precision.

In DECODE mode, users are not asked to provide a precision level because this information is contained in the length of
Geohash values given.