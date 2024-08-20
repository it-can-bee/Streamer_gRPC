有幸得到冲哥指点 非常感谢～欢迎交流

我的主页：[博客园](https://www.cnblogs.com/live-passion)

# gRPC

gRPC与RPC最大区别是它支持跨语言。本质都是调用方提供参数去调用，被调用方的调用机器上的程序这样的一种调用服务方式。

**gRPC是类似于Json、且为协议缓冲区大小不超过几兆字节的结构化数据提供序列化格式的一种机制**

RPC：给你一个RPC的ip+端口（这也是为什么编写客户端的时候需要先建立链接，就是在模仿rpc调用，proto定义的service就是rpc给你提供的方法，客户端对应的调用其方法就可以去拿到对应的响应数据），然后用户可以利用它与服务器建立链接，然后再发送请求，调用对应的远程服务调用方法，然后服务器给客户端进行响应

# 谷歌推出的proto
通过在proto文件里边定义了序列化数据结构,在通过根目录的build.rs以后得到一个Builder类，通过这个类可以进行实例化操作，也就是说包括序列化数据的解析等


# 项目执行：
```cargo run --bin server```
```cargo run --bin client```

# 运行结果：
```
client ...
================================================
    Finished `dev` profile [unoptimized + debuginfo] target(s) in 2.42s
     Running `target/debug/client`
*** SIMPLE RPC ***
RESPONSE = Response { metadata: MetadataMap { headers: {"content-type": "application/grpc", "date": "Tue, 20 Aug 2024 08:37:22 GMT", "grpc-status": "0"} }, message: Feature { name: "Berkshire Valley Management Area Trail, Jefferson, NJ, USA", location: Some(Point { latitude: 409146138, longitude: -746188906 }) }, extensions: Extensions }

*** SERVER STREAMING ***
NOTE = Feature { name: "Patriots Path, Mendham, NJ 07945, USA", location: Some(Point { latitude: 407838351, longitude: -746143763 }) }
NOTE = Feature { name: "101 New Jersey 10, Whippany, NJ 07981, USA", location: Some(Point { latitude: 408122808, longitude: -743999179 }) }
NOTE = Feature { name: "U.S. 6, Shohola, PA 18458, USA", location: Some(Point { latitude: 413628156, longitude: -749015468 }) }
NOTE = Feature { name: "5 Conners Road, Kingston, NY 12401, USA", location: Some(Point { latitude: 419999544, longitude: -740371136 }) }
NOTE = Feature { name: "Mid Hudson Psychiatric Center, New Hampton, NY 10958, USA", location: Some(Point { latitude: 414008389, longitude: -743951297 }) }
NOTE = Feature { name: "287 Flugertown Road, Livingston Manor, NY 12758, USA", location: Some(Point { latitude: 419611318, longitude: -746524769 }) }
NOTE = Feature { name: "4001 Tremley Point Road, Linden, NJ 07036, USA", location: Some(Point { latitude: 406109563, longitude: -742186778 }) }
NOTE = Feature { name: "352 South Mountain Road, Wallkill, NY 12589, USA", location: Some(Point { latitude: 416802456, longitude: -742370183 }) }
NOTE = Feature { name: "Bailey Turn Road, Harriman, NY 10926, USA", location: Some(Point { latitude: 412950425, longitude: -741077389 }) }
NOTE = Feature { name: "193-199 Wawayanda Road, Hewitt, NJ 07421, USA", location: Some(Point { latitude: 412144655, longitude: -743949739 }) }
NOTE = Feature { name: "406-496 Ward Avenue, Pine Bush, NY 12566, USA", location: Some(Point { latitude: 415736605, longitude: -742847522 }) }
NOTE = Feature { name: "162 Merrill Road, Highland Mills, NY 10930, USA", location: Some(Point { latitude: 413843930, longitude: -740501726 }) }
NOTE = Feature { name: "Clinton Road, West Milford, NJ 07480, USA", location: Some(Point { latitude: 410873075, longitude: -744459023 }) }
NOTE = Feature { name: "16 Old Brook Lane, Warwick, NY 10990, USA", location: Some(Point { latitude: 412346009, longitude: -744026814 }) }
NOTE = Feature { name: "3 Drake Lane, Pennington, NJ 08534, USA", location: Some(Point { latitude: 402948455, longitude: -747903913 }) }
NOTE = Feature { name: "6324 8th Avenue, Brooklyn, NY 11220, USA", location: Some(Point { latitude: 406337092, longitude: -740122226 }) }
NOTE = Feature { name: "1 Merck Access Road, Whitehouse Station, NJ 08889, USA", location: Some(Point { latitude: 406421967, longitude: -747727624 }) }
NOTE = Feature { name: "78-98 Schalck Road, Narrowsburg, NY 12764, USA", location: Some(Point { latitude: 416318082, longitude: -749677716 }) }
NOTE = Feature { name: "282 Lakeview Drive Road, Highland Lake, NY 12743, USA", location: Some(Point { latitude: 415301720, longitude: -748416257 }) }
NOTE = Feature { name: "330 Evelyn Avenue, Hamilton Township, NJ 08619, USA", location: Some(Point { latitude: 402647019, longitude: -747071791 }) }
NOTE = Feature { name: "New York State Reference Route 987E, Southfields, NY 10975, USA", location: Some(Point { latitude: 412567807, longitude: -741058078 }) }
NOTE = Feature { name: "103-271 Tempaloni Road, Ellenville, NY 12428, USA", location: Some(Point { latitude: 416855156, longitude: -744420597 }) }
NOTE = Feature { name: "1300 Airport Road, North Brunswick Township, NJ 08902, USA", location: Some(Point { latitude: 404663628, longitude: -744820157 }) }
NOTE = Feature { name: "", location: Some(Point { latitude: 407113723, longitude: -749746483 }) }
NOTE = Feature { name: "", location: Some(Point { latitude: 402133926, longitude: -743613249 }) }
NOTE = Feature { name: "", location: Some(Point { latitude: 400273442, longitude: -741220915 }) }
NOTE = Feature { name: "", location: Some(Point { latitude: 411236786, longitude: -744070769 }) }
NOTE = Feature { name: "211-225 Plains Road, Augusta, NJ 07822, USA", location: Some(Point { latitude: 411633782, longitude: -746784970 }) }
NOTE = Feature { name: "", location: Some(Point { latitude: 415830701, longitude: -742952812 }) }
NOTE = Feature { name: "165 Pedersen Ridge Road, Milford, PA 18337, USA", location: Some(Point { latitude: 413447164, longitude: -748712898 }) }
NOTE = Feature { name: "100-122 Locktown Road, Frenchtown, NJ 08825, USA", location: Some(Point { latitude: 405047245, longitude: -749800722 }) }
NOTE = Feature { name: "", location: Some(Point { latitude: 418858923, longitude: -746156790 }) }
NOTE = Feature { name: "650-652 Willi Hill Road, Swan Lake, NY 12783, USA", location: Some(Point { latitude: 417951888, longitude: -748484944 }) }
NOTE = Feature { name: "26 East 3rd Street, New Providence, NJ 07974, USA", location: Some(Point { latitude: 407033786, longitude: -743977337 }) }
NOTE = Feature { name: "", location: Some(Point { latitude: 417548014, longitude: -740075041 }) }
NOTE = Feature { name: "", location: Some(Point { latitude: 410395868, longitude: -744972325 }) }
NOTE = Feature { name: "", location: Some(Point { latitude: 404615353, longitude: -745129803 }) }
NOTE = Feature { name: "611 Lawrence Avenue, Westfield, NJ 07090, USA", location: Some(Point { latitude: 406589790, longitude: -743560121 }) }
NOTE = Feature { name: "18 Lannis Avenue, New Windsor, NY 12553, USA", location: Some(Point { latitude: 414653148, longitude: -740477477 }) }
NOTE = Feature { name: "82-104 Amherst Avenue, Colonia, NJ 07067, USA", location: Some(Point { latitude: 405957808, longitude: -743255336 }) }
NOTE = Feature { name: "170 Seven Lakes Drive, Sloatsburg, NY 10974, USA", location: Some(Point { latitude: 411733589, longitude: -741648093 }) }
NOTE = Feature { name: "1270 Lakes Road, Monroe, NY 10950, USA", location: Some(Point { latitude: 412676291, longitude: -742606606 }) }
NOTE = Feature { name: "509-535 Alphano Road, Great Meadows, NJ 07838, USA", location: Some(Point { latitude: 409224445, longitude: -748286738 }) }
NOTE = Feature { name: "652 Garden Street, Elizabeth, NJ 07202, USA", location: Some(Point { latitude: 406523420, longitude: -742135517 }) }
NOTE = Feature { name: "349 Sea Spray Court, Neptune City, NJ 07753, USA", location: Some(Point { latitude: 401827388, longitude: -740294537 }) }
NOTE = Feature { name: "13-17 Stanley Street, West Milford, NJ 07480, USA", location: Some(Point { latitude: 410564152, longitude: -743685054 }) }
NOTE = Feature { name: "47 Industrial Avenue, Teterboro, NJ 07608, USA", location: Some(Point { latitude: 408472324, longitude: -740726046 }) }
NOTE = Feature { name: "5 White Oak Lane, Stony Point, NY 10980, USA", location: Some(Point { latitude: 412452168, longitude: -740214052 }) }
NOTE = Feature { name: "Berkshire Valley Management Area Trail, Jefferson, NJ, USA", location: Some(Point { latitude: 409146138, longitude: -746188906 }) }
NOTE = Feature { name: "1007 Jersey Avenue, New Brunswick, NJ 08901, USA", location: Some(Point { latitude: 404701380, longitude: -744781745 }) }
NOTE = Feature { name: "6 East Emerald Isle Drive, Lake Hopatcong, NJ 07849, USA", location: Some(Point { latitude: 409642566, longitude: -746017679 }) }
NOTE = Feature { name: "1358-1474 New Jersey 57, Port Murray, NJ 07865, USA", location: Some(Point { latitude: 408031728, longitude: -748645385 }) }
NOTE = Feature { name: "367 Prospect Road, Chester, NY 10918, USA", location: Some(Point { latitude: 413700272, longitude: -742135189 }) }
NOTE = Feature { name: "10 Simon Lake Drive, Atlantic Highlands, NJ 07716, USA", location: Some(Point { latitude: 404310607, longitude: -740282632 }) }
NOTE = Feature { name: "11 Ward Street, Mount Arlington, NJ 07856, USA", location: Some(Point { latitude: 409319800, longitude: -746201391 }) }
NOTE = Feature { name: "300-398 Jefferson Avenue, Elizabeth, NJ 07201, USA", location: Some(Point { latitude: 406685311, longitude: -742108603 }) }
NOTE = Feature { name: "43 Dreher Road, Roscoe, NY 12776, USA", location: Some(Point { latitude: 419018117, longitude: -749142781 }) }
NOTE = Feature { name: "Swan Street, Pine Island, NY 10969, USA", location: Some(Point { latitude: 412856162, longitude: -745148837 }) }
NOTE = Feature { name: "66 Pleasantview Avenue, Monticello, NY 12701, USA", location: Some(Point { latitude: 416560744, longitude: -746721964 }) }
NOTE = Feature { name: "", location: Some(Point { latitude: 405314270, longitude: -749836354 }) }
NOTE = Feature { name: "", location: Some(Point { latitude: 414219548, longitude: -743327440 }) }
NOTE = Feature { name: "565 Winding Hills Road, Montgomery, NY 12549, USA", location: Some(Point { latitude: 415534177, longitude: -742900616 }) }
NOTE = Feature { name: "231 Rocky Run Road, Glen Gardner, NJ 08826, USA", location: Some(Point { latitude: 406898530, longitude: -749127080 }) }
NOTE = Feature { name: "100 Mount Pleasant Avenue, Newark, NJ 07104, USA", location: Some(Point { latitude: 407586880, longitude: -741670168 }) }
NOTE = Feature { name: "517-521 Huntington Drive, Manchester Township, NJ 08759, USA", location: Some(Point { latitude: 400106455, longitude: -742870190 }) }
NOTE = Feature { name: "", location: Some(Point { latitude: 400066188, longitude: -746793294 }) }
NOTE = Feature { name: "40 Mountain Road, Napanoch, NY 12458, USA", location: Some(Point { latitude: 418803880, longitude: -744102673 }) }
NOTE = Feature { name: "", location: Some(Point { latitude: 414204288, longitude: -747895140 }) }
NOTE = Feature { name: "", location: Some(Point { latitude: 414777405, longitude: -740615601 }) }
NOTE = Feature { name: "48 North Road, Forestburgh, NY 12777, USA", location: Some(Point { latitude: 415464475, longitude: -747175374 }) }
NOTE = Feature { name: "", location: Some(Point { latitude: 404062378, longitude: -746376177 }) }
NOTE = Feature { name: "", location: Some(Point { latitude: 405688272, longitude: -749285130 }) }
NOTE = Feature { name: "", location: Some(Point { latitude: 400342070, longitude: -748788996 }) }
NOTE = Feature { name: "", location: Some(Point { latitude: 401809022, longitude: -744157964 }) }
NOTE = Feature { name: "9 Thompson Avenue, Leonardo, NJ 07737, USA", location: Some(Point { latitude: 404226644, longitude: -740517141 }) }
NOTE = Feature { name: "", location: Some(Point { latitude: 410322033, longitude: -747871659 }) }
NOTE = Feature { name: "", location: Some(Point { latitude: 407100674, longitude: -747742727 }) }
NOTE = Feature { name: "213 Bush Road, Stone Ridge, NY 12484, USA", location: Some(Point { latitude: 418811433, longitude: -741718005 }) }
NOTE = Feature { name: "", location: Some(Point { latitude: 415034302, longitude: -743850945 }) }
NOTE = Feature { name: "", location: Some(Point { latitude: 411349992, longitude: -743694161 }) }
NOTE = Feature { name: "1-17 Bergen Court, New Brunswick, NJ 08901, USA", location: Some(Point { latitude: 404839914, longitude: -744759616 }) }
NOTE = Feature { name: "35 Oakland Valley Road, Cuddebackville, NY 12729, USA", location: Some(Point { latitude: 414638017, longitude: -745957854 }) }
NOTE = Feature { name: "", location: Some(Point { latitude: 412127800, longitude: -740173578 }) }
NOTE = Feature { name: "", location: Some(Point { latitude: 401263460, longitude: -747964303 }) }
NOTE = Feature { name: "", location: Some(Point { latitude: 412843391, longitude: -749086026 }) }
NOTE = Feature { name: "", location: Some(Point { latitude: 418512773, longitude: -743067823 }) }
NOTE = Feature { name: "42-102 Main Street, Belford, NJ 07718, USA", location: Some(Point { latitude: 404318328, longitude: -740835638 }) }
NOTE = Feature { name: "", location: Some(Point { latitude: 419020746, longitude: -741172328 }) }
NOTE = Feature { name: "", location: Some(Point { latitude: 404080723, longitude: -746119569 }) }
NOTE = Feature { name: "", location: Some(Point { latitude: 401012643, longitude: -744035134 }) }
NOTE = Feature { name: "", location: Some(Point { latitude: 404306372, longitude: -741079661 }) }
NOTE = Feature { name: "", location: Some(Point { latitude: 403966326, longitude: -748519297 }) }
NOTE = Feature { name: "", location: Some(Point { latitude: 405002031, longitude: -748407866 }) }
NOTE = Feature { name: "", location: Some(Point { latitude: 409532885, longitude: -742200683 }) }
NOTE = Feature { name: "", location: Some(Point { latitude: 416851321, longitude: -742674555 }) }
NOTE = Feature { name: "3387 Richmond Terrace, Staten Island, NY 10303, USA", location: Some(Point { latitude: 406411633, longitude: -741722051 }) }
NOTE = Feature { name: "261 Van Sickle Road, Goshen, NY 10924, USA", location: Some(Point { latitude: 413069058, longitude: -744597778 }) }
NOTE = Feature { name: "", location: Some(Point { latitude: 418465462, longitude: -746859398 }) }
NOTE = Feature { name: "", location: Some(Point { latitude: 411733222, longitude: -744228360 }) }
NOTE = Feature { name: "3 Hasta Way, Newton, NJ 07860, USA", location: Some(Point { latitude: 410248224, longitude: -747127767 }) }

*** CLIENT STREAMING ***
Traversing 90 points
SUMMARY: RouteSummary { point_count: 90, feature_count: 0, distance: 847295907, elapsed_time: 0 }

*** BIDIRECTIONAL STREAMING ***
NOTE = RouteNote { location: Some(Point { latitude: 409146138, longitude: -746188906 }), message: "at 209.286µs" }
NOTE = RouteNote { location: Some(Point { latitude: 409146139, longitude: -746188906 }), message: "at 1.000209286s" }
NOTE = RouteNote { location: Some(Point { latitude: 409146140, longitude: -746188906 }), message: "at 2.000209286s" }
NOTE = RouteNote { location: Some(Point { latitude: 409146141, longitude: -746188906 }), message: "at 3.000209286s" }
NOTE = RouteNote { location: Some(Point { latitude: 409146142, longitude: -746188906 }), message: "at 4.000209286s" }
NOTE = RouteNote { location: Some(Point { latitude: 409146143, longitude: -746188906 }), message: "at 5.000209286s" }
NOTE = RouteNote { location: Some(Point { latitude: 409146144, longitude: -746188906 }), message: "at 6.000209286s" }
NOTE = RouteNote { location: Some(Point { latitude: 409146145, longitude: -746188906 }), message: "at 7.000209286s" }
NOTE = RouteNote { location: Some(Point { latitude: 409146146, longitude: -746188906 }), message: "at 8.000209286s" }
NOTE = RouteNote { location: Some(Point { latitude: 409146147, longitude: -746188906 }), message: "at 9.000209286s" }
NOTE = RouteNote { location: Some(Point { latitude: 409146148, longitude: -746188906 }), message: "at 10.000209286s" }
NOTE = RouteNote { location: Some(Point { latitude: 409146149, longitude: -746188906 }), message: "at 11.000209286s" }
NOTE = RouteNote { location: Some(Point { latitude: 409146150, longitude: -746188906 }), message: "at 12.000209286s" }
NOTE = RouteNote { location: Some(Point { latitude: 409146151, longitude: -746188906 }), message: "at 13.000209286s" }
NOTE = RouteNote { location: Some(Point { latitude: 409146152, longitude: -746188906 }), message: "at 14.000209286s" }
NOTE = RouteNote { location: Some(Point { latitude: 409146153, longitude: -746188906 }), message: "at 15.000209286s" }
NOTE = RouteNote { location: Some(Point { latitude: 409146154, longitude: -746188906 }), message: "at 16.000209286s" }
......
```
```
server ...
================================================
    Finished `dev` profile [unoptimized + debuginfo] target(s) in 5.03s
     Running `target/debug/server`
GetFeature = Request { metadata: MetadataMap { headers: {"te": "trailers", "content-type": "application/grpc", "user-agent": "tonic/0.12.1"} }, message: Point { latitude: 409146138, longitude: -746188906 }, extensions: Extensions }
ListFeatures = Request { metadata: MetadataMap { headers: {"te": "trailers", "content-type": "application/grpc", "user-agent": "tonic/0.12.1"} }, message: Rectangle { lo: Some(Point { latitude: 400000000, longitude: -750000000 }), hi: Some(Point { latitude: 420000000, longitude: -730000000 }) }, extensions: Extensions }
  => send Feature { name: "Patriots Path, Mendham, NJ 07945, USA", location: Some(Point { latitude: 407838351, longitude: -746143763 }) }
  => send Feature { name: "101 New Jersey 10, Whippany, NJ 07981, USA", location: Some(Point { latitude: 408122808, longitude: -743999179 }) }
  => send Feature { name: "U.S. 6, Shohola, PA 18458, USA", location: Some(Point { latitude: 413628156, longitude: -749015468 }) }
  => send Feature { name: "5 Conners Road, Kingston, NY 12401, USA", location: Some(Point { latitude: 419999544, longitude: -740371136 }) }
  => send Feature { name: "Mid Hudson Psychiatric Center, New Hampton, NY 10958, USA", location: Some(Point { latitude: 414008389, longitude: -743951297 }) }
  => send Feature { name: "287 Flugertown Road, Livingston Manor, NY 12758, USA", location: Some(Point { latitude: 419611318, longitude: -746524769 }) }
  => send Feature { name: "4001 Tremley Point Road, Linden, NJ 07036, USA", location: Some(Point { latitude: 406109563, longitude: -742186778 }) }
  => send Feature { name: "352 South Mountain Road, Wallkill, NY 12589, USA", location: Some(Point { latitude: 416802456, longitude: -742370183 }) }
  => send Feature { name: "Bailey Turn Road, Harriman, NY 10926, USA", location: Some(Point { latitude: 412950425, longitude: -741077389 }) }
  => send Feature { name: "193-199 Wawayanda Road, Hewitt, NJ 07421, USA", location: Some(Point { latitude: 412144655, longitude: -743949739 }) }
  => send Feature { name: "406-496 Ward Avenue, Pine Bush, NY 12566, USA", location: Some(Point { latitude: 415736605, longitude: -742847522 }) }
  => send Feature { name: "162 Merrill Road, Highland Mills, NY 10930, USA", location: Some(Point { latitude: 413843930, longitude: -740501726 }) }
  => send Feature { name: "Clinton Road, West Milford, NJ 07480, USA", location: Some(Point { latitude: 410873075, longitude: -744459023 }) }
  => send Feature { name: "16 Old Brook Lane, Warwick, NY 10990, USA", location: Some(Point { latitude: 412346009, longitude: -744026814 }) }
  => send Feature { name: "3 Drake Lane, Pennington, NJ 08534, USA", location: Some(Point { latitude: 402948455, longitude: -747903913 }) }
  => send Feature { name: "6324 8th Avenue, Brooklyn, NY 11220, USA", location: Some(Point { latitude: 406337092, longitude: -740122226 }) }
  => send Feature { name: "1 Merck Access Road, Whitehouse Station, NJ 08889, USA", location: Some(Point { latitude: 406421967, longitude: -747727624 }) }
  => send Feature { name: "78-98 Schalck Road, Narrowsburg, NY 12764, USA", location: Some(Point { latitude: 416318082, longitude: -749677716 }) }
  => send Feature { name: "282 Lakeview Drive Road, Highland Lake, NY 12743, USA", location: Some(Point { latitude: 415301720, longitude: -748416257 }) }
  => send Feature { name: "330 Evelyn Avenue, Hamilton Township, NJ 08619, USA", location: Some(Point { latitude: 402647019, longitude: -747071791 }) }
  ......
```

