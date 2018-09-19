# xcode-build-times-rendering
Xcode build times visualization per target
![image](https://user-images.githubusercontent.com/119268/45782819-abd2aa00-bc6c-11e8-9ee0-114c020f238a.png)

# Installation
In order to use this one, you'll need to install [xcodeproj](https://www.rubydoc.info/gems/xcodeproj) gem
```
[sudo] gem install xcodeproj
```
# Injection
In order to gather target build times, we're about to add build phases "START" and "END" for **EACH** target in **EACH** project at specified path.
```
./xcode-build-times.rb install ~/Projects/<My_slowly_building_project>/
```
![image](https://user-images.githubusercontent.com/119268/45782420-898c5c80-bc6b-11e8-9200-d54dbc5ea56f.png)

# Events
After installation, all build events will be saved to `~/.timings.xcode` file
```
...
{"date":"2018-09-19T22:52:04.1537386724", "taskName":"A", "event":"start"},
{"date":"2018-09-19T22:53:01.1537386781", "taskName":"A", "event":"end"},
{"date":"2018-09-19T22:53:04.1537386784", "taskName":"B", "event":"start"},
{"date":"2018-09-19T22:55:53.1537386953", "taskName":"V", "event":"end"},
...
```

# Generating Visualization Events
Once desired build is done, it's time to dump raw events in place we need in order to render them.
This can be done by running
```
./xcode-build-times.rb generate
```

# Open gantt.html
It's time to see results. Just open **gantt.html** inside this project.

## Libraries and Kudos
[d3js](https://d3js.org/) - JavaScript library for manipulating documents based on data  
[xcodeproj](https://github.com/CocoaPods/Xcodeproj) - Create and modify Xcode projects from Ruby.  
[d3js-gantt](https://github.com/dk8996/Gantt-Chart) - Gantt chart for d3js by [@dk8996](https://github.com/dk8996)

