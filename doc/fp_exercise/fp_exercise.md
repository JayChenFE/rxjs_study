
<!-- TOC -->

- [说明](#说明)
- [Traversing an Array](#traversing-an-array)
    - [Exercise 1: Print all the names in an array](#exercise-1-print-all-the-names-in-an-array)
    - [Exercise 2: Use forEach to print all the names in an array](#exercise-2-use-foreach-to-print-all-the-names-in-an-array)
- [Projecting Arrays](#projecting-arrays)
    - [Exercise 3: Project an array of videos into an array of {id,title} pairs using forEach()](#exercise-3-project-an-array-of-videos-into-an-array-of-idtitle-pairs-using-foreach)
    - [Exercise 4: Implement map()](#exercise-4-implement-map)
    - [Exercise 5: Use map() to project an array of videos into an array of {id,title} pairs](#exercise-5-use-map-to-project-an-array-of-videos-into-an-array-of-idtitle-pairs)
- [Filtering Arrays](#filtering-arrays)
    - [Exercise 6: Use forEach() to collect only those videos with a rating of 5.0](#exercise-6-use-foreach-to-collect-only-those-videos-with-a-rating-of-50)
    - [Exercise 7: Implement filter()](#exercise-7-implement-filter)
- [Query Data by Chaining Method Calls](#query-data-by-chaining-method-calls)
    - [Exercise 8: Chain filter and map to collect the ids of videos that have a rating of 5.0](#exercise-8-chain-filter-and-map-to-collect-the-ids-of-videos-that-have-a-rating-of-50)
- [Querying Trees](#querying-trees)
    - [Exercise 9: Flatten the movieLists array into an array of video ids](#exercise-9-flatten-the-movielists-array-into-an-array-of-video-ids)
    - [Exercise 10: Implement concatAll()](#exercise-10-implement-concatall)
    - [Exercise 10-1: 拍平数组](#exercise-10-1-拍平数组)
    - [Exercise 11: Use map() and concatAll() to project and flatten the movieLists into an array of video ids](#exercise-11-use-map-and-concatall-to-project-and-flatten-the-movielists-into-an-array-of-video-ids)
    - [Exercise 12: Retrieve id, title, and a 150x200 box art url for every video](#exercise-12-retrieve-id-title-and-a-150x200-box-art-url-for-every-video)
    - [Exercise 13: Implement concatMap()](#exercise-13-implement-concatmap)
    - [Exercise 14: Use concatMap() to retrieve id, title, and 150x200 box art url for every video](#exercise-14-use-concatmap-to-retrieve-id-title-and-150x200-box-art-url-for-every-video)
- [Reducing Arrays](#reducing-arrays)
    - [Exercise 15: Use forEach to find the largest box art](#exercise-15-use-foreach-to-find-the-largest-box-art)
    - [Exercise 16: Implement reduce()](#exercise-16-implement-reduce)
    - [Exercise 17: Retrieve the largest rating.](#exercise-17-retrieve-the-largest-rating)
    - [Exercise 18: Retrieve url of the largest boxart](#exercise-18-retrieve-url-of-the-largest-boxart)
    - [Exercise 19: Reducing with an initial value](#exercise-19-reducing-with-an-initial-value)
    - [Exercise 20: Retrieve the id, title, and smallest box art url for every video.](#exercise-20-retrieve-the-id-title-and-smallest-box-art-url-for-every-video)
- [Zipping Arrays](#zipping-arrays)
    - [Exercise 21: Combine videos and bookmarks by index](#exercise-21-combine-videos-and-bookmarks-by-index)
    - [Exercise 22: Implement zip](#exercise-22-implement-zip)
    - [Exercise 23: Combine videos and bookmarks by index](#exercise-23-combine-videos-and-bookmarks-by-index)
    - [Exercise 24: Retrieve each video's id, title, middle interesting moment time, and smallest box art url.](#exercise-24-retrieve-each-videos-id-title-middle-interesting-moment-time-and-smallest-box-art-url)
- [Powerful Queries](#powerful-queries)
    - [Exercise 25: Converting from Arrays to Trees](#exercise-25-converting-from-arrays-to-trees)
    - [Exercise 26: Converting from Arrays to Deeper Trees](#exercise-26-converting-from-arrays-to-deeper-trees)
    - [Exercise 27: Stock Ticker](#exercise-27-stock-ticker)
- [Working with Observables](#working-with-observables)
    - [Exercise 28: Subscribing to an event](#exercise-28-subscribing-to-an-event)
    - [Exercise 29: Traversing an Event](#exercise-29-traversing-an-event)
    - [Exercise 30: Completing Sequences with take()](#exercise-30-completing-sequences-with-take)
    - [Exercise 31: Completing sequences with takeUntil()](#exercise-31-completing-sequences-with-takeuntil)
- [Querying Observables](#querying-observables)
    - [Exercise 32: Creating a mouse drag event](#exercise-32-creating-a-mouse-drag-event)
    - [Exercise 33: Improving our mouse drag event](#exercise-33-improving-our-mouse-drag-event)
    - [Exercise 34: HTTP requests](#exercise-34-http-requests)
    - [Exercise 35: Sequencing HTTP requests with callbacks](#exercise-35-sequencing-http-requests-with-callbacks)
    - [Exercise 36: Traversing callback-based Asynchronous APIs](#exercise-36-traversing-callback-based-asynchronous-apis)
    - [Exercise 37: Sequencing HTTP requests with Observable](#exercise-37-sequencing-http-requests-with-observable)
    - [Exercise 38: Throttle Input](#exercise-38-throttle-input)
    - [Exercise 38: Throttle Input](#exercise-38-throttle-input-1)
    - [Exercise 39: Autocomplete Box](#exercise-39-autocomplete-box)
    - [Exercise 40: Distinct Until Changed Input](#exercise-40-distinct-until-changed-input)
    - [Exercise 41: Autocomplete Box Part 2: Electric Boogaloo](#exercise-41-autocomplete-box-part-2-electric-boogaloo)
    - [Exercise 42: Retrying after errors](#exercise-42-retrying-after-errors)

<!-- /TOC -->
# 说明
学习响应式编程，题目地址为[http://reactivex.io/learnrx/](http://reactivex.io/learnrx/)
# Traversing an Array
## Exercise 1: Print all the names in an array

```javascript
function(console) {
	var names = ["Ben", "Jafar", "Matt", "Priya", "Brian"],
		counter;

	for(counter = 0; counter < names.length; counter++) {
		console.log(names[counter]);
	}
}
```
## Exercise 2: Use forEach to print all the names in an array

Let's repeat the previous exercise using the forEach function.
```javascript
function(console) {
	var names = ["Ben", "Jafar", "Matt", "Priya", "Brian"];

	names.forEach(function(name) {
		console.log(name);
	});
}
```
# Projecting Arrays
## Exercise 3: Project an array of videos into an array of {id,title} pairs using forEach()
For each video, add a projected {id, title} pair to the videoAndTitlePairs array.
```javascript
function() {
	var newReleases = [
			{
				"id": 70111470,
				"title": "Die Hard",
				"boxart": "http://cdn-0.nflximg.com/images/2891/DieHard.jpg",
				"uri": "http://api.netflix.com/catalog/titles/movies/70111470",
				"rating": [4.0],
				"bookmark": []
			},
			{
				"id": 654356453,
				"title": "Bad Boys",
				"boxart": "http://cdn-0.nflximg.com/images/2891/BadBoys.jpg",
				"uri": "http://api.netflix.com/catalog/titles/movies/70111470",
				"rating": [5.0],
				"bookmark": [{ id: 432534, time: 65876586 }]
			},
			{
				"id": 65432445,
				"title": "The Chamber",
				"boxart": "http://cdn-0.nflximg.com/images/2891/TheChamber.jpg",
				"uri": "http://api.netflix.com/catalog/titles/movies/70111470",
				"rating": [4.0],
				"bookmark": []
			},
			{
				"id": 675465,
				"title": "Fracture",
				"boxart": "http://cdn-0.nflximg.com/images/2891/Fracture.jpg",
				"uri": "http://api.netflix.com/catalog/titles/movies/70111470",
				"rating": [5.0],
				"bookmark": [{ id: 432534, time: 65876586 }]
			}
		],
		videoAndTitlePairs = [];

	newReleases.forEach(function(video) {
		videoAndTitlePairs.push({
			id: video.id,
			title: video.title
		});
	});

	return videoAndTitlePairs;
}
```
## Exercise 4: Implement map()

To make projections easier, let's add a map() function to the Array type. Map accepts the projection function to be applied to each item in the source array, and returns the projected array.
```javascript
Array.prototype.map = function(projectionFunction) {
	var results = [];
	this.forEach(function(itemInArray) {
		results.push(projectionFunction(itemInArray));

	});

	return results;
};

// JSON.stringify([1,2,3].map(function(x) { return x + 1; })) === '[2,3,4]'
		
```

## Exercise 5: Use map() to project an array of videos into an array of {id,title} pairs

Let's repeat the exercise of collecting {id, title} pairs for each video in the newReleases array, but this time we'll use our map function.
```javascript
function() {
	var newReleases = [
			{
				"id": 70111470,
				"title": "Die Hard",
				"boxart": "http://cdn-0.nflximg.com/images/2891/DieHard.jpg",
				"uri": "http://api.netflix.com/catalog/titles/movies/70111470",
				"rating": [4.0],
				"bookmark": []
			},
			{
				"id": 654356453,
				"title": "Bad Boys",
				"boxart": "http://cdn-0.nflximg.com/images/2891/BadBoys.jpg",
				"uri": "http://api.netflix.com/catalog/titles/movies/70111470",
				"rating": [5.0],
				"bookmark": [{ id: 432534, time: 65876586 }]
			},
			{
				"id": 65432445,
				"title": "The Chamber",
				"boxart": "http://cdn-0.nflximg.com/images/2891/TheChamber.jpg",
				"uri": "http://api.netflix.com/catalog/titles/movies/70111470",
				"rating": [4.0],
				"bookmark": []
			},
			{
				"id": 675465,
				"title": "Fracture",
				"boxart": "http://cdn-0.nflximg.com/images/2891/Fracture.jpg",
				"uri": "http://api.netflix.com/catalog/titles/movies/70111470",
				"rating": [5.0],
				"bookmark": [{ id: 432534, time: 65876586 }]
			}
		];

   return newReleases.map(function(video) {
 	return {
 		id: video.id,
 		title: video.title
 	};
 });
}
```
# Filtering Arrays
## Exercise 6: Use forEach() to collect only those videos with a rating of 5.0

Use forEach() to loop through the videos in the newReleases array and, if a video has a rating of 5.0, add it to the videos array.
```javascript
function() {
	var newReleases = [
			{
				"id": 70111470,
				"title": "Die Hard",
				"boxart": "http://cdn-0.nflximg.com/images/2891/DieHard.jpg",
				"uri": "http://api.netflix.com/catalog/titles/movies/70111470",
				"rating": 4.0,
				"bookmark": []
			},
			{
				"id": 654356453,
				"title": "Bad Boys",
				"boxart": "http://cdn-0.nflximg.com/images/2891/BadBoys.jpg",
				"uri": "http://api.netflix.com/catalog/titles/movies/70111470",
				"rating": 5.0,
				"bookmark": [{ id: 432534, time: 65876586 }]
			},
			{
				"id": 65432445,
				"title": "The Chamber",
				"boxart": "http://cdn-0.nflximg.com/images/2891/TheChamber.jpg",
				"uri": "http://api.netflix.com/catalog/titles/movies/70111470",
				"rating": 4.0,
				"bookmark": []
			},
			{
				"id": 675465,
				"title": "Fracture",
				"boxart": "http://cdn-0.nflximg.com/images/2891/Fracture.jpg",
				"uri": "http://api.netflix.com/catalog/titles/movies/70111470",
				"rating": 5.0,
				"bookmark": [{ id: 432534, time: 65876586 }]
			}
		],
		videos = [];

	newReleases.forEach(function(video) {
		if (video.rating === 5.0) {
			videos.push(video);
		}
	});

	return videos;
}
```
## Exercise 7: Implement filter()

To make filtering easier, let's add a filter() function to the Array type. The filter() function accepts a predicate. A predicate is a function that accepts an item in the array, and returns a boolean indicating whether the item should be retained in the new array.

```javascript
Array.prototype.filter = function(predicateFunction) {
	var results = [];
	this.forEach(function(itemInArray) {
	  if (predicateFunction(itemInArray)) {
		results.push(itemInArray);
	  }
	});

	return results;
};

// JSON.stringify([1,2,3].filter(function(x) { return x > 2})) === "[3]"
```

# Query Data by Chaining Method Calls
## Exercise 8: Chain filter and map to collect the ids of videos that have a rating of 5.0
```javascript
function() {
	var newReleases = [
		{
			"id": 70111470,
			"title": "Die Hard",
			"boxart": "http://cdn-0.nflximg.com/images/2891/DieHard.jpg",
			"uri": "http://api.netflix.com/catalog/titles/movies/70111470",
			"rating": 4.0,
			"bookmark": []
		},
		{
			"id": 654356453,
			"title": "Bad Boys",
			"boxart": "http://cdn-0.nflximg.com/images/2891/BadBoys.jpg",
			"uri": "http://api.netflix.com/catalog/titles/movies/70111470",
			"rating": 5.0,
			"bookmark": [{ id: 432534, time: 65876586 }]
		},
		{
			"id": 65432445,
			"title": "The Chamber",
			"boxart": "http://cdn-0.nflximg.com/images/2891/TheChamber.jpg",
			"uri": "http://api.netflix.com/catalog/titles/movies/70111470",
			"rating": 4.0,
			"bookmark": []
		},
		{
			"id": 675465,
			"title": "Fracture",
			"boxart": "http://cdn-0.nflximg.com/images/2891/Fracture.jpg",
			"uri": "http://api.netflix.com/catalog/titles/movies/70111470",
			"rating": 5.0,
			"bookmark": [{ id: 432534, time: 65876586 }]
		}
	];

	// ------------ INSERT CODE HERE! -----------------------------------
	// Chain the filter and map functions to select the id of all videos
	// with a rating of 5.0.

	return newReleases // Complete this expression
	// ------------ INSERT CODE HERE! -----------------------------------
}
		
```
```javascript
function() {
	var newReleases = [{
		"id": 70111470,
		"title": "Die Hard",
		"boxart": "http://cdn-0.nflximg.com/images/2891/DieHard.jpg",
		"uri": "http://api.netflix.com/catalog/titles/movies/70111470",
		"rating": 4.0,
		"bookmark": []
	}, {
		"id": 654356453,
		"title": "Bad Boys",
		"boxart": "http://cdn-0.nflximg.com/images/2891/BadBoys.jpg",
		"uri": "http://api.netflix.com/catalog/titles/movies/70111470",
		"rating": 5.0,
		"bookmark": [{
			id: 432534,
			time: 65876586
		}]
	}, {
		"id": 65432445,
		"title": "The Chamber",
		"boxart": "http://cdn-0.nflximg.com/images/2891/TheChamber.jpg",
		"uri": "http://api.netflix.com/catalog/titles/movies/70111470",
		"rating": 4.0,
		"bookmark": []
	}, {
		"id": 675465,
		"title": "Fracture",
		"boxart": "http://cdn-0.nflximg.com/images/2891/Fracture.jpg",
		"uri": "http://api.netflix.com/catalog/titles/movies/70111470",
		"rating": 5.0,
		"bookmark": [{
			id: 432534,
			time: 65876586
		}]
	}];

	// ------------ INSERT CODE HERE! -----------------------------------
	// Chain the filter and map functions to select the id of all videos
	// with a rating of 5.0.

	return newReleases.filter(item => item.rating === 5.0)
		.map(item => item.id);

	// Complete this expression
	// ------------ INSERT CODE HERE! -----------------------------------
}
```
# Querying Trees
## Exercise 9: Flatten the movieLists array into an array of video ids

Let's start by using two nested forEach loops to collect the id of every video in the two-dimensional movieLists array.
```javascript
function() {
	var movieLists = [
		{
			name: "New Releases",
			videos: [
				{
					"id": 70111470,
					"title": "Die Hard",
					"boxart": "http://cdn-0.nflximg.com/images/2891/DieHard.jpg",
					"uri": "http://api.netflix.com/catalog/titles/movies/70111470",
					"rating": 4.0,
					"bookmark": []
				},
				{
					"id": 654356453,
					"title": "Bad Boys",
					"boxart": "http://cdn-0.nflximg.com/images/2891/BadBoys.jpg",
					"uri": "http://api.netflix.com/catalog/titles/movies/70111470",
					"rating": 5.0,
					"bookmark": [{ id: 432534, time: 65876586 }]
				}
			]
		},
		{
			name: "Dramas",
			videos: [
				{
					"id": 65432445,
					"title": "The Chamber",
					"boxart": "http://cdn-0.nflximg.com/images/2891/TheChamber.jpg",
					"uri": "http://api.netflix.com/catalog/titles/movies/70111470",
					"rating": 4.0,
					"bookmark": []
				},
				{
					"id": 675465,
					"title": "Fracture",
					"boxart": "http://cdn-0.nflximg.com/images/2891/Fracture.jpg",
					"uri": "http://api.netflix.com/catalog/titles/movies/70111470",
					"rating": 5.0,
					"bookmark": [{ id: 432534, time: 65876586 }]
				}
			]
		}
	],
	allVideoIdsInMovieLists = [];

	// ------------   INSERT CODE HERE!  -----------------------------------
	// Use two nested forEach loops to flatten the movieLists into a list of
	// video ids.
	// ------------   INSERT CODE HERE!  -----------------------------------

	return allVideoIdsInMovieLists;

}
```
```javascript
function() {
	var movieLists = [{
			name: "New Releases",
			videos: [{
				"id": 70111470,
				"title": "Die Hard",
				"boxart": "http://cdn-0.nflximg.com/images/2891/DieHard.jpg",
				"uri": "http://api.netflix.com/catalog/titles/movies/70111470",
				"rating": 4.0,
				"bookmark": []
			}, {
				"id": 654356453,
				"title": "Bad Boys",
				"boxart": "http://cdn-0.nflximg.com/images/2891/BadBoys.jpg",
				"uri": "http://api.netflix.com/catalog/titles/movies/70111470",
				"rating": 5.0,
				"bookmark": [{
					id: 432534,
					time: 65876586
				}]
			}]
		}, {
			name: "Dramas",
			videos: [{
				"id": 65432445,
				"title": "The Chamber",
				"boxart": "http://cdn-0.nflximg.com/images/2891/TheChamber.jpg",
				"uri": "http://api.netflix.com/catalog/titles/movies/70111470",
				"rating": 4.0,
				"bookmark": []
			}, {
				"id": 675465,
				"title": "Fracture",
				"boxart": "http://cdn-0.nflximg.com/images/2891/Fracture.jpg",
				"uri": "http://api.netflix.com/catalog/titles/movies/70111470",
				"rating": 5.0,
				"bookmark": [{
					id: 432534,
					time: 65876586
				}]
			}]
		}],
		allVideoIdsInMovieLists = [];
	movieLists.forEach((list) => {
		allVideoIdsInMovieLists = allVideoIdsInMovieLists.concat(list.videos.map((video) => video.id));
	});
	// ------------   INSERT CODE HERE!  -----------------------------------
	// Use two nested forEach loops to flatten the movieLists into a list of
	// video ids.
	// ------------   INSERT CODE HERE!  -----------------------------------

	return allVideoIdsInMovieLists;

}
```
## Exercise 10: Implement concatAll()

Let's add a concatAll() function to the Array type. The concatAll() function iterates over each sub-array in the array and collects the results in a new, flat array. Notice that **the concatAll() function expects each item in the array to be another array.**

```javascript
Array.prototype.concatAll = function() {
	var results = [];
	this.forEach(function(subArray) {
		// ------------ INSERT CODE HERE! ----------------------------
		// Add all the items in each subArray to the results array.
		// ------------ INSERT CODE HERE! ----------------------------
	});

	return results;
};

// JSON.stringify([ [1,2,3], [4,5,6], [7,8,9] ].concatAll()) === "[1,2,3,4,5,6,7,8,9]"
// [1,2,3].concatAll(); // throws an error because this is a one-dimensional array
```

## Exercise 10-1: 拍平数组
```javascript
function flatten(arr) {

	var results = [];
	arr.forEach(function(item) {

		if (Array.isArray(item)) {
			results = results.concat(flatten(item));
		} else {
			results.push(item);
		}
	});

	return results;

}

var a=[2, 3, 4, [5],
	[6, 7],
	[8, [9, 10]],
	[11, [12, [13, [14, [15]]]]]
]


flatten(a)
//(14) [2, 3, 4, 5, 6, 7, 8, 9, 10, 11, 12, 13, 14, 15]

```
```javascript
Array.prototype.flatten = Array.prototype.flatten || function() {
	var results = [];
	this.forEach(function(item) {
		// ------------ INSERT CODE HERE! ----------------------------
		// Add all the items in each subArray to the results array.
		// ------------ INSERT CODE HERE! ----------------------------
		if (Array.isArray(item)) {
			results = results.concat(item.flatten());
		} else {
			results.push(item);
		}
	});

	return results;
};

// JSON.stringify([ [1,2,3], [4,5,6], [7,8,9] ].concatAll()) === "[1,2,3,4,5,6,7,8,9]"
// [1,2,3].concatAll(); // throws an error because this is a one-dimensional array

[
	[1, 2], 3, 4, [5],
	[6, 7],
	[8, [9, 10]],
	[11, [12, [13, [14, [15]]]]]
].flatten();
//(15) [1, 2, 3, 4, 5, 6, 7, 8, 9, 10, 11, 12, 13, 14, 15]
```
## Exercise 11: Use map() and concatAll() to project and flatten the movieLists into an array of video ids

Hint: use two nested calls to map() and one call to concatAll().
```javascript
function() {
	var movieLists = [
			{
				name: "New Releases",
				videos: [
					{
						"id": 70111470,
						"title": "Die Hard",
						"boxart": "http://cdn-0.nflximg.com/images/2891/DieHard.jpg",
						"uri": "http://api.netflix.com/catalog/titles/movies/70111470",
						"rating": 4.0,
						"bookmark": []
					},
					{
						"id": 654356453,
						"title": "Bad Boys",
						"boxart": "http://cdn-0.nflximg.com/images/2891/BadBoys.jpg",
						"uri": "http://api.netflix.com/catalog/titles/movies/70111470",
						"rating": 5.0,
						"bookmark": [{ id: 432534, time: 65876586 }]
					}
				]
			},
			{
				name: "Dramas",
				videos: [
					{
						"id": 65432445,
						"title": "The Chamber",
						"boxart": "http://cdn-0.nflximg.com/images/2891/TheChamber.jpg",
						"uri": "http://api.netflix.com/catalog/titles/movies/70111470",
						"rating": 4.0,
						"bookmark": []
					},
					{
						"id": 675465,
						"title": "Fracture",
						"boxart": "http://cdn-0.nflximg.com/images/2891/Fracture.jpg",
						"uri": "http://api.netflix.com/catalog/titles/movies/70111470",
						"rating": 5.0,
						"bookmark": [{ id: 432534, time: 65876586 }]
					}
				]
			}
		];

	// ------------   INSERT CODE HERE!  -----------------------------------
	// Use map and concatAll to flatten the movieLists in a list of video ids.
	// ------------   INSERT CODE HERE!  -----------------------------------

	return movieLists // Complete this expression!

}
```
```javascript
function() {
	var movieLists = [{
		name: "New Releases",
		videos: [{
			"id": 70111470,
			"title": "Die Hard",
			"boxart": "http://cdn-0.nflximg.com/images/2891/DieHard.jpg",
			"uri": "http://api.netflix.com/catalog/titles/movies/70111470",
			"rating": 4.0,
			"bookmark": []
		}, {
			"id": 654356453,
			"title": "Bad Boys",
			"boxart": "http://cdn-0.nflximg.com/images/2891/BadBoys.jpg",
			"uri": "http://api.netflix.com/catalog/titles/movies/70111470",
			"rating": 5.0,
			"bookmark": [{
				id: 432534,
				time: 65876586
			}]
		}]
	}, {
		name: "Dramas",
		videos: [{
			"id": 65432445,
			"title": "The Chamber",
			"boxart": "http://cdn-0.nflximg.com/images/2891/TheChamber.jpg",
			"uri": "http://api.netflix.com/catalog/titles/movies/70111470",
			"rating": 4.0,
			"bookmark": []
		}, {
			"id": 675465,
			"title": "Fracture",
			"boxart": "http://cdn-0.nflximg.com/images/2891/Fracture.jpg",
			"uri": "http://api.netflix.com/catalog/titles/movies/70111470",
			"rating": 5.0,
			"bookmark": [{
				id: 432534,
				time: 65876586
			}]
		}]
	}];

	// ------------   INSERT CODE HERE!  -----------------------------------
	// Use map and concatAll to flatten the movieLists in a list of video ids.
	// ------------   INSERT CODE HERE!  -----------------------------------

	// return movieLists.map(list => list.videos)
	// 	.concatAll()
	// 	.map(video => video.id); // Complete this expression!

	return movieLists.map((list) => {
			return list.videos.map(video => video.id)
		})
		.concatAll();
}
```

## Exercise 12: Retrieve id, title, and a 150x200 box art url for every video

You've managed to flatten a tree that's two levels deep, let's try for three! Let's say that instead of a single boxart url on each video, we had a collection of boxart objects, each with a different size and url. Create a query that selects {id, title, boxart} for every video in the movieLists. This time though, the boxart property in the result will be the url of the boxart object with dimensions of 150x200px. Let's see if you can solve this problem with map(), concatAll(), and filter().

There's just more one thing: you `can't` use indexers. In other words, this is `illegal`:

```javascript
var itemInArray = movieLists[0];
```
Furthermore, you're not allowed to use indexers in any of the remaining exercises unless you're implementing one of the five functions. There is a very good reason for this restriction, and that reason will eventually be explained. For now, you'll simply have to accept it on faith that this restriction serves a purpose. :-)

```javascript
function() {
	var movieLists = [
			{
				name: "Instant Queue",
				videos : [
					{
						"id": 70111470,
						"title": "Die Hard",
						"boxarts": [
							{ width: 150, height: 200, url: "http://cdn-0.nflximg.com/images/2891/DieHard150.jpg" },
							{ width: 200, height: 200, url: "http://cdn-0.nflximg.com/images/2891/DieHard200.jpg" }
						],
						"url": "http://api.netflix.com/catalog/titles/movies/70111470",
						"rating": 4.0,
						"bookmark": []
					},
					{
						"id": 654356453,
						"title": "Bad Boys",
						"boxarts": [
							{ width: 200, height: 200, url: "http://cdn-0.nflximg.com/images/2891/BadBoys200.jpg" },
							{ width: 150, height: 200, url: "http://cdn-0.nflximg.com/images/2891/BadBoys150.jpg" }

						],
						"url": "http://api.netflix.com/catalog/titles/movies/70111470",
						"rating": 5.0,
						"bookmark": [{ id: 432534, time: 65876586 }]
					}
				]
			},
			{
				name: "New Releases",
				videos: [
					{
						"id": 65432445,
						"title": "The Chamber",
						"boxarts": [
							{ width: 150, height: 200, url: "http://cdn-0.nflximg.com/images/2891/TheChamber150.jpg" },
							{ width: 200, height: 200, url: "http://cdn-0.nflximg.com/images/2891/TheChamber200.jpg" }
						],
						"url": "http://api.netflix.com/catalog/titles/movies/70111470",
						"rating": 4.0,
						"bookmark": []
					},
					{
						"id": 675465,
						"title": "Fracture",
						"boxarts": [
							{ width: 200, height: 200, url: "http://cdn-0.nflximg.com/images/2891/Fracture200.jpg" },
							{ width: 150, height: 200, url: "http://cdn-0.nflximg.com/images/2891/Fracture150.jpg" },
							{ width: 300, height: 200, url: "http://cdn-0.nflximg.com/images/2891/Fracture300.jpg" }
						],
						"url": "http://api.netflix.com/catalog/titles/movies/70111470",
						"rating": 5.0,
						"bookmark": [{ id: 432534, time: 65876586 }]
					}
				]
			}
		];


	// Use one or more map, concatAll, and filter calls to create an array with the following items
	// [
	//	 {"id": 675465,"title": "Fracture","boxart":"http://cdn-0.nflximg.com/images/2891/Fracture150.jpg" },
	//	 {"id": 65432445,"title": "The Chamber","boxart":"http://cdn-0.nflximg.com/images/2891/TheChamber150.jpg" },
	//	 {"id": 654356453,"title": "Bad Boys","boxart":"http://cdn-0.nflximg.com/images/2891/BadBoys150.jpg" },
	//	 {"id": 70111470,"title": "Die Hard","boxart":"http://cdn-0.nflximg.com/images/2891/DieHard150.jpg" }
	// ];

	return movieLists // Complete this expression!

}
```
```javascript
function() {
	var movieLists = [{
		name: "Instant Queue",
		videos: [{
			"id": 70111470,
			"title": "Die Hard",
			"boxarts": [{
				width: 150,
				height: 200,
				url: "http://cdn-0.nflximg.com/images/2891/DieHard150.jpg"
			}, {
				width: 200,
				height: 200,
				url: "http://cdn-0.nflximg.com/images/2891/DieHard200.jpg"
			}],
			"url": "http://api.netflix.com/catalog/titles/movies/70111470",
			"rating": 4.0,
			"bookmark": []
		}, {
			"id": 654356453,
			"title": "Bad Boys",
			"boxarts": [{
					width: 200,
					height: 200,
					url: "http://cdn-0.nflximg.com/images/2891/BadBoys200.jpg"
				}, {
					width: 150,
					height: 200,
					url: "http://cdn-0.nflximg.com/images/2891/BadBoys150.jpg"
				}

			],
			"url": "http://api.netflix.com/catalog/titles/movies/70111470",
			"rating": 5.0,
			"bookmark": [{
				id: 432534,
				time: 65876586
			}]
		}]
	}, {
		name: "New Releases",
		videos: [{
			"id": 65432445,
			"title": "The Chamber",
			"boxarts": [{
				width: 150,
				height: 200,
				url: "http://cdn-0.nflximg.com/images/2891/TheChamber150.jpg"
			}, {
				width: 200,
				height: 200,
				url: "http://cdn-0.nflximg.com/images/2891/TheChamber200.jpg"
			}],
			"url": "http://api.netflix.com/catalog/titles/movies/70111470",
			"rating": 4.0,
			"bookmark": []
		}, {
			"id": 675465,
			"title": "Fracture",
			"boxarts": [{
				width: 200,
				height: 200,
				url: "http://cdn-0.nflximg.com/images/2891/Fracture200.jpg"
			}, {
				width: 150,
				height: 200,
				url: "http://cdn-0.nflximg.com/images/2891/Fracture150.jpg"
			}, {
				width: 300,
				height: 200,
				url: "http://cdn-0.nflximg.com/images/2891/Fracture300.jpg"
			}],
			"url": "http://api.netflix.com/catalog/titles/movies/70111470",
			"rating": 5.0,
			"bookmark": [{
				id: 432534,
				time: 65876586
			}]
		}]
	}];


	// Use one or more map, concatAll, and filter calls to create an array with the following items
	// [
	//	 {"id": 675465,"title": "Fracture","boxart":"http://cdn-0.nflximg.com/images/2891/Fracture150.jpg" },
	//	 {"id": 65432445,"title": "The Chamber","boxart":"http://cdn-0.nflximg.com/images/2891/TheChamber150.jpg" },
	//	 {"id": 654356453,"title": "Bad Boys","boxart":"http://cdn-0.nflximg.com/images/2891/BadBoys150.jpg" },
	//	 {"id": 70111470,"title": "Die Hard","boxart":"http://cdn-0.nflximg.com/images/2891/DieHard150.jpg" }
	// ];

	return movieLists.map(list => {
			return list.videos.map(video => {
					return video.boxarts.filter(boxart => boxart.width === 150 && boxart.height === 200)
						.map(boxart => {
							return {
								id: video.id,
								title: video.title,
								boxart: boxart.url
							};
						});
				})
				.concatAll();
		})
		.concatAll(); // Complete this expression!

}
```

Fantastic job! Now you've learned to use concatAll() alongside map() and filter() to query trees. Notice that **map() and concatAll() are very commonly chained together**. Let's create a small helper function to help us with this common pattern.

## Exercise 13: Implement concatMap()

Nearly every time we flatten a tree we chain map() and concatAll(). Sometimes, if we're dealing with a tree several levels deep, we'll repeat this combination many times in our code. To save on typing, let's create a concatMap function that's just a map operation, followed by a concatAll.

```javascript
Array.prototype.concatMap = function(projectionFunctionThatReturnsArray) {
	return this.
		map(function(item) {
			// ------------   INSERT CODE HERE!  ----------------------------
			// Apply the projection function to each item. The projection
			// function will return a new child array. This will create a
			// two-dimensional array.
			// ------------   INSERT CODE HERE!  ----------------------------
		}).
		// apply the concatAll function to flatten the two-dimensional array
		concatAll();
};

/*
	var spanishFrenchEnglishWords = [ ["cero","rien","zero"], ["uno","un","one"], ["dos","deux","two"] ];
	// collect all the words for each number, in every language, in a single, flat list
	var allWords = [0,1,2].
		concatMap(function(index) {
			return spanishFrenchEnglishWords[index];
		});

	return JSON.stringify(allWords) === '["cero","rien","zero","uno","un","one","dos","deux","two"]';
*/
	
```
```javascript
Array.prototype.concatMap = function(projectionFunctionThatReturnsArray) {
	return this.
	map(item => projectionFunctionThatReturnsArray(item)
			// ------------   INSERT CODE HERE!  ----------------------------
			// Apply the projection function to each item. The projection
			// function will return a new child array. This will create a
			// two-dimensional array.
			// ------------   INSERT CODE HERE!  ----------------------------
		).
		// apply the concatAll function to flatten the two-dimensional array
	concatAll();
};

/*
	var spanishFrenchEnglishWords = [ ["cero","rien","zero"], ["uno","un","one"], ["dos","deux","two"] ];
	// collect all the words for each number, in every language, in a single, flat list
	var allWords = [0,1,2].
		concatMap(function(index) {
			return spanishFrenchEnglishWords[index];
		});

	return JSON.stringify(allWords) === '["cero","rien","zero","uno","un","one","dos","deux","two"]';
*/
```
##Exercise 14: Use concatMap() to retrieve id, title, and 150x200 box art url for every video

Let's repeat the exercise we just performed. However this time we'll simplify the code by replacing the map().concatAll() calls with concatMap().
```javascript
function() {
	var movieLists = [
			{
				name: "Instant Queue",
				videos : [
					{
						"id": 70111470,
						"title": "Die Hard",
						"boxarts": [
							{ width: 150, height: 200, url: "http://cdn-0.nflximg.com/images/2891/DieHard150.jpg" },
							{ width: 200, height: 200, url: "http://cdn-0.nflximg.com/images/2891/DieHard200.jpg" }
						],
						"url": "http://api.netflix.com/catalog/titles/movies/70111470",
						"rating": 4.0,
						"bookmark": []
					},
					{
						"id": 654356453,
						"title": "Bad Boys",
						"boxarts": [
							{ width: 200, height: 200, url: "http://cdn-0.nflximg.com/images/2891/BadBoys200.jpg" },
							{ width: 150, height: 200, url: "http://cdn-0.nflximg.com/images/2891/BadBoys150.jpg" }

						],
						"url": "http://api.netflix.com/catalog/titles/movies/70111470",
						"rating": 5.0,
						"bookmark": [{ id: 432534, time: 65876586 }]
					}
				]
			},
			{
				name: "New Releases",
				videos: [
					{
						"id": 65432445,
						"title": "The Chamber",
						"boxarts": [
							{ width: 150, height: 200, url: "http://cdn-0.nflximg.com/images/2891/TheChamber150.jpg" },
							{ width: 200, height: 200, url: "http://cdn-0.nflximg.com/images/2891/TheChamber200.jpg" }
						],
						"url": "http://api.netflix.com/catalog/titles/movies/70111470",
						"rating": 4.0,
						"bookmark": []
					},
					{
						"id": 675465,
						"title": "Fracture",
						"boxarts": [
							{ width: 200, height: 200, url: "http://cdn-0.nflximg.com/images/2891/Fracture200.jpg" },
							{ width: 150, height: 200, url: "http://cdn-0.nflximg.com/images/2891/Fracture150.jpg" },
							{ width: 300, height: 200, url: "http://cdn-0.nflximg.com/images/2891/Fracture300.jpg" }
						],
						"url": "http://api.netflix.com/catalog/titles/movies/70111470",
						"rating": 5.0,
						"bookmark": [{ id: 432534, time: 65876586 }]
					}
				]
			}
		];


	// Use one or more concatMap, map, and filter calls to create an array with the following items
	// [
	//	 {"id": 675465, "title": "Fracture", "boxart": "http://cdn-0.nflximg.com/images/2891/Fracture150.jpg" },
	//	 {"id": 65432445, "title": "The Chamber", "boxart": "http://cdn-0.nflximg.com/images/2891/TheChamber150.jpg" },
	//	 {"id": 654356453, "title": "Bad Boys", "boxart": "http://cdn-0.nflximg.com/images/2891/BadBoys150.jpg" },
	//	 {"id": 70111470, "title": "Die Hard", "boxart": "http://cdn-0.nflximg.com/images/2891/DieHard150.jpg" }
	// ];

	return movieLists // Complete this expression!

}
```
```javascript
function() {
	var movieLists = [{
		name: "Instant Queue",
		videos: [{
			"id": 70111470,
			"title": "Die Hard",
			"boxarts": [{
				width: 150,
				height: 200,
				url: "http://cdn-0.nflximg.com/images/2891/DieHard150.jpg"
			}, {
				width: 200,
				height: 200,
				url: "http://cdn-0.nflximg.com/images/2891/DieHard200.jpg"
			}],
			"url": "http://api.netflix.com/catalog/titles/movies/70111470",
			"rating": 4.0,
			"bookmark": []
		}, {
			"id": 654356453,
			"title": "Bad Boys",
			"boxarts": [{
					width: 200,
					height: 200,
					url: "http://cdn-0.nflximg.com/images/2891/BadBoys200.jpg"
				}, {
					width: 150,
					height: 200,
					url: "http://cdn-0.nflximg.com/images/2891/BadBoys150.jpg"
				}

			],
			"url": "http://api.netflix.com/catalog/titles/movies/70111470",
			"rating": 5.0,
			"bookmark": [{
				id: 432534,
				time: 65876586
			}]
		}]
	}, {
		name: "New Releases",
		videos: [{
			"id": 65432445,
			"title": "The Chamber",
			"boxarts": [{
				width: 150,
				height: 200,
				url: "http://cdn-0.nflximg.com/images/2891/TheChamber150.jpg"
			}, {
				width: 200,
				height: 200,
				url: "http://cdn-0.nflximg.com/images/2891/TheChamber200.jpg"
			}],
			"url": "http://api.netflix.com/catalog/titles/movies/70111470",
			"rating": 4.0,
			"bookmark": []
		}, {
			"id": 675465,
			"title": "Fracture",
			"boxarts": [{
				width: 200,
				height: 200,
				url: "http://cdn-0.nflximg.com/images/2891/Fracture200.jpg"
			}, {
				width: 150,
				height: 200,
				url: "http://cdn-0.nflximg.com/images/2891/Fracture150.jpg"
			}, {
				width: 300,
				height: 200,
				url: "http://cdn-0.nflximg.com/images/2891/Fracture300.jpg"
			}],
			"url": "http://api.netflix.com/catalog/titles/movies/70111470",
			"rating": 5.0,
			"bookmark": [{
				id: 432534,
				time: 65876586
			}]
		}]
	}];


	// Use one or more concatMap, map, and filter calls to create an array with the following items
	// [
	//	 {"id": 675465, "title": "Fracture", "boxart": "http://cdn-0.nflximg.com/images/2891/Fracture150.jpg" },
	//	 {"id": 65432445, "title": "The Chamber", "boxart": "http://cdn-0.nflximg.com/images/2891/TheChamber150.jpg" },
	//	 {"id": 654356453, "title": "Bad Boys", "boxart": "http://cdn-0.nflximg.com/images/2891/BadBoys150.jpg" },
	//	 {"id": 70111470, "title": "Die Hard", "boxart": "http://cdn-0.nflximg.com/images/2891/DieHard150.jpg" }
	// ];

	return movieLists.concatMap(list => {
		return list.videos.concatMap(video => video.boxarts
			.filter(boxart => boxart.width === 150 && boxart.height === 200)
			.map(boxart => {
				return {
					id: video.id,
					title: video.title,
					boxart: boxart.url
				};
			}));
	}); // Complete this expression!

}
```
# Reducing Arrays
Sometimes we need to perform an operation on more than one item in the array at the same time. For example, let's say we need to find the largest integer in an array. We can't use a filter() operation, because it only examines one item at a time. To find the largest integer we need to compare items in the array to each other.

One approach could be to select an item in the array as the assumed largest number (perhaps the first item), and then compare that value to every other item in the array. Each time we come across a number that was larger than our assumed largest number, we'd replace it with the larger value, and continue the process until the entire array was traversed.

If we replaced the specific size comparison with a closure, we could write a function that handled the array traversal process for us. At each step our function would apply the closure to the last value and the current value and use the result as the last value the next time. Finally we'd be left with only one value. This process is known as reducing because we reduce many values to a single value.

## Exercise 15: Use forEach to find the largest box art

In this example we use forEach to find the largest box art. Each time we examine a new boxart we update a variable with the currently known maximumSize. If the boxart is smaller than the maximum size, we discard it. If it's larger, we keep track of it. Finally we're left with a single boxart which must necessarily be the largest.

```javascript
function() {
	var boxarts = [
			{ width: 200, height: 200, url: "http://cdn-0.nflximg.com/images/2891/Fracture200.jpg" },
			{ width: 150, height: 200, url: "http://cdn-0.nflximg.com/images/2891/Fracture150.jpg" },
			{ width: 300, height: 200, url: "http://cdn-0.nflximg.com/images/2891/Fracture300.jpg" },
			{ width: 425, height: 150, url: "http://cdn-0.nflximg.com/images/2891/Fracture425.jpg" }
		],
		currentSize,
		maxSize = -1,
		largestBoxart;

	boxarts.forEach(function(boxart) {
		currentSize = boxart.width * boxart.height;
		if (currentSize > maxSize) {
			largestBoxart = boxart;
			maxSize = currentSize;
		}
	});

	return largestBoxart;
}
```
## Exercise 16: Implement reduce()

Let's add a reduce() function to the Array type. Like map. Take note **this is different from the reduce in ES5**, which returns a value instead of an Array!
```javascript
// [1,2,3].reduce(function(accumulatedValue, currentValue) { return accumulatedValue + currentValue; }); === [6];
// [1,2,3].reduce(function(accumulatedValue, currentValue) { return accumulatedValue + currentValue; }, 10); === [16];

Array.prototype.reduce = function(combiner, initialValue) {
	var counter,
		accumulatedValue;

	// If the array is empty, do nothing
	if (this.length === 0) {
		return this;
	}
	else {
		// If the user didn't pass an initial value, use the first item.
		if (arguments.length === 1) {
			counter = 1;
			accumulatedValue = this[0];
		}
		else if (arguments.length >= 2) {
			counter = 0;
			accumulatedValue = initialValue;
		}
		else {
			throw "Invalid arguments.";
		}

		// Loop through the array, feeding the current value and the result of
		// the previous computation back into the combiner function until
		// we've exhausted the entire array and are left with only one value.
		while(counter < this.length) {
			accumulatedValue = combiner(accumulatedValue, this[counter])
			counter++;
		}

		return [accumulatedValue];
	}
};
```
## Exercise 17: Retrieve the largest rating.

Let's use our new reduce function to isolate the largest value in an array of ratings.
```javascript
function() {
	var ratings = [2,3,1,4,5];

	// You should return an array containing only the largest rating. Remember that reduce always
	// returns an array with one item.
	return ratings.
		reduce   // Complete this expression
}
```

```javascript
function() {
	var ratings = [2, 3, 1, 4, 5];

	// You should return an array containing only the largest rating. Remember that reduce always
	// returns an array with one item.
	return ratings.reduce((acc, curr) => Math.max(acc, curr)); // Complete this expression
}
```
## Exercise 18: Retrieve url of the largest boxart

Let's try combining reduce() with map() to reduce multiple boxart objects to a single value: the url of the largest box art.
```javascript
function() {
	var boxarts = [
			{ width: 200, height: 200, url: "http://cdn-0.nflximg.com/images/2891/Fracture200.jpg" },
			{ width: 150, height: 200, url: "http://cdn-0.nflximg.com/images/2891/Fracture150.jpg" },
			{ width: 300, height: 200, url: "http://cdn-0.nflximg.com/images/2891/Fracture300.jpg" },
			{ width: 425, height: 150, url: "http://cdn-0.nflximg.com/images/2891/Fracture425.jpg" }
		];

	// You should return an array containing only the URL of the largest box art. Remember that reduce always
	// returns an array with one item.
	return boxarts.
		reduce   // Complete this expression
}
```

```javascript
function() {
	var boxarts = [{
		width: 200,
		height: 200,
		url: "http://cdn-0.nflximg.com/images/2891/Fracture200.jpg"
	}, {
		width: 150,
		height: 200,
		url: "http://cdn-0.nflximg.com/images/2891/Fracture150.jpg"
	}, {
		width: 300,
		height: 200,
		url: "http://cdn-0.nflximg.com/images/2891/Fracture300.jpg"
	}, {
		width: 425,
		height: 150,
		url: "http://cdn-0.nflximg.com/images/2891/Fracture425.jpg"
	}];

	// You should return an array containing only the URL of the largest box art. Remember that reduce always
	// returns an array with one item.
	return boxarts.reduce((acc, curr) => (acc.width * acc.height > curr.height * curr.width ? acc : curr).url); // Complete this expression
}

```

## Exercise 19: Reducing with an initial value

Sometimes when we reduce an array, we want the reduced value to be a different type than the items stored in the array. Let's say we have an array of videos and we want to reduce them to a single map where the key is the video id and the value is the video's title.
```javascript
function() {
	var videos = [
		{
			"id": 65432445,
			"title": "The Chamber"
		},
		{
			"id": 675465,
			"title": "Fracture"
		},
		{
			"id": 70111470,
			"title": "Die Hard"
		},
		{
			"id": 654356453,
			"title": "Bad Boys"
		}
	];

	// Expecting this output...
	// [
	//	 {
	//		 "65432445": "The Chamber",
	//		 "675465": "Fracture",
	//		 "70111470": "Die Hard",
	//		 "654356453": "Bad Boys"
	//	 }
	// ]
	return videos.
		reduce(function(accumulatedMap, video) {
		var obj = {};

		// ----- INSERT CODE TO ADD THE VIDEO TITLE TO THE ----
		// ----- NEW MAP USING THE VIDEO ID AS THE KEY	 ----

		// Object.assign() takes all of the enumerable properties from
		// the object listed in its second argument (obj) and assigns them
		// to the object listed in its first argument (accumulatedMap).
		return Object.assign(accumulatedMap, obj);
		},
		// Use an empty map as the initial value instead of the first item in
		// the list.
		{});
}
```
```javascript
function() {
	var videos = [{
		"id": 65432445,
		"title": "The Chamber"
	}, {
		"id": 675465,
		"title": "Fracture"
	}, {
		"id": 70111470,
		"title": "Die Hard"
	}, {
		"id": 654356453,
		"title": "Bad Boys"
	}];

	// Expecting this output...
	// [
	//	 {
	//		 "65432445": "The Chamber",
	//		 "675465": "Fracture",
	//		 "70111470": "Die Hard",
	//		 "654356453": "Bad Boys"
	//	 }
	// ]
	return videos.
	reduce((accumulatedMap, video) => {
			var obj = {};
			obj[video.id] = video.title;

			// ----- INSERT CODE TO ADD THE VIDEO TITLE TO THE ----
			// ----- NEW MAP USING THE VIDEO ID AS THE KEY	 ----

			// Object.assign() takes all of the enumerable properties from
			// the object listed in its second argument (obj) and assigns them
			// to the object listed in its first argument (accumulatedMap).
			return Object.assign(accumulatedMap, obj);
		},
		// Use an empty map as the initial value instead of the first item in
		// the list.
		{});
}
```

## Exercise 20: Retrieve the id, title, and smallest box art url for every video.

This is a variation of the problem we solved earlier, where we retrieved the url of the boxart with a width of 150px. This time we'll use reduce() instead of filter() to retrieve the *smallest* box art in the boxarts array.
```javascript
function() {
	var movieLists = [
		{
			name: "New Releases",
			videos: [
				{
					"id": 70111470,
					"title": "Die Hard",
					"boxarts": [
						{ width: 150, height:200, url:"http://cdn-0.nflximg.com/images/2891/DieHard150.jpg" },
						{ width: 200, height:200, url:"http://cdn-0.nflximg.com/images/2891/DieHard200.jpg" }
					],
					"url": "http://api.netflix.com/catalog/titles/movies/70111470",
					"rating": 4.0,
					"bookmark": []
				},
				{
					"id": 654356453,
					"title": "Bad Boys",
					"boxarts": [
						{ width: 200, height:200, url:"http://cdn-0.nflximg.com/images/2891/BadBoys200.jpg" },
						{ width: 140, height:200, url:"http://cdn-0.nflximg.com/images/2891/BadBoys140.jpg" }

					],
					"url": "http://api.netflix.com/catalog/titles/movies/70111470",
					"rating": 5.0,
					"bookmark": [{ id:432534, time:65876586 }]
				}
			]
		},
		{
			name: "Thrillers",
			videos: [
				{
					"id": 65432445,
					"title": "The Chamber",
					"boxarts": [
						{ width: 130, height:200, url:"http://cdn-0.nflximg.com/images/2891/TheChamber130.jpg" },
						{ width: 200, height:200, url:"http://cdn-0.nflximg.com/images/2891/TheChamber200.jpg" }
					],
					"url": "http://api.netflix.com/catalog/titles/movies/70111470",
					"rating": 4.0,
					"bookmark": []
				},
				{
					"id": 675465,
					"title": "Fracture",
					"boxarts": [
						{ width: 200, height:200, url:"http://cdn-0.nflximg.com/images/2891/Fracture200.jpg" },
						{ width: 120, height:200, url:"http://cdn-0.nflximg.com/images/2891/Fracture120.jpg" },
						{ width: 300, height:200, url:"http://cdn-0.nflximg.com/images/2891/Fracture300.jpg" }
					],
					"url": "http://api.netflix.com/catalog/titles/movies/70111470",
					"rating": 5.0,
					"bookmark": [{ id:432534, time:65876586 }]
				}
			]
		}
	];


	// Use one or more concatMap, map, and reduce calls to create an array with the following items (order doesn't matter)
	// [
	//	 {"id": 675465,"title": "Fracture","boxart":"http://cdn-0.nflximg.com/images/2891/Fracture120.jpg" },
	//	 {"id": 65432445,"title": "The Chamber","boxart":"http://cdn-0.nflximg.com/images/2891/TheChamber130.jpg" },
	//	 {"id": 654356453,"title": "Bad Boys","boxart":"http://cdn-0.nflximg.com/images/2891/BadBoys140.jpg" },
	//	 {"id": 70111470,"title": "Die Hard","boxart":"http://cdn-0.nflximg.com/images/2891/DieHard150.jpg" }
	// ];

	return movieLists.
		concatMap(function(movieList) {

		})

}
```

```javascript
function() {
	var movieLists = [{
		name: "New Releases",
		videos: [{
			"id": 70111470,
			"title": "Die Hard",
			"boxarts": [{
				width: 150,
				height: 200,
				url: "http://cdn-0.nflximg.com/images/2891/DieHard150.jpg"
			}, {
				width: 200,
				height: 200,
				url: "http://cdn-0.nflximg.com/images/2891/DieHard200.jpg"
			}],
			"url": "http://api.netflix.com/catalog/titles/movies/70111470",
			"rating": 4.0,
			"bookmark": []
		}, {
			"id": 654356453,
			"title": "Bad Boys",
			"boxarts": [{
					width: 200,
					height: 200,
					url: "http://cdn-0.nflximg.com/images/2891/BadBoys200.jpg"
				}, {
					width: 140,
					height: 200,
					url: "http://cdn-0.nflximg.com/images/2891/BadBoys140.jpg"
				}

			],
			"url": "http://api.netflix.com/catalog/titles/movies/70111470",
			"rating": 5.0,
			"bookmark": [{
				id: 432534,
				time: 65876586
			}]
		}]
	}, {
		name: "Thrillers",
		videos: [{
			"id": 65432445,
			"title": "The Chamber",
			"boxarts": [{
				width: 130,
				height: 200,
				url: "http://cdn-0.nflximg.com/images/2891/TheChamber130.jpg"
			}, {
				width: 200,
				height: 200,
				url: "http://cdn-0.nflximg.com/images/2891/TheChamber200.jpg"
			}],
			"url": "http://api.netflix.com/catalog/titles/movies/70111470",
			"rating": 4.0,
			"bookmark": []
		}, {
			"id": 675465,
			"title": "Fracture",
			"boxarts": [{
				width: 200,
				height: 200,
				url: "http://cdn-0.nflximg.com/images/2891/Fracture200.jpg"
			}, {
				width: 120,
				height: 200,
				url: "http://cdn-0.nflximg.com/images/2891/Fracture120.jpg"
			}, {
				width: 300,
				height: 200,
				url: "http://cdn-0.nflximg.com/images/2891/Fracture300.jpg"
			}],
			"url": "http://api.netflix.com/catalog/titles/movies/70111470",
			"rating": 5.0,
			"bookmark": [{
				id: 432534,
				time: 65876586
			}]
		}]
	}];


	// Use one or more concatMap, map, and reduce calls to create an array with the following items (order doesn't matter)
	// [
	//	 {"id": 675465,"title": "Fracture","boxart":"http://cdn-0.nflximg.com/images/2891/Fracture120.jpg" },
	//	 {"id": 65432445,"title": "The Chamber","boxart":"http://cdn-0.nflximg.com/images/2891/TheChamber130.jpg" },
	//	 {"id": 654356453,"title": "Bad Boys","boxart":"http://cdn-0.nflximg.com/images/2891/BadBoys140.jpg" },
	//	 {"id": 70111470,"title": "Die Hard","boxart":"http://cdn-0.nflximg.com/images/2891/DieHard150.jpg" }
	// ];

	return movieLists.
	concatMap(list => {
			return list.videos.concatMap(video => video.boxarts
				.reduce((acc, curr) => (acc.width * acc.height < curr.width * curr.height) ? acc : curr)
				.map(boxart => {
					return {
						id: video.id,
						title: video.title,
						boxart: boxart.url
					};
				}));
		}

	);
}
```

# Zipping Arrays
Sometimes we need to combine two arrays by progressively taking an item from each and combining the pair. If you visualize a zipper, where each side is an array, and each tooth is an item, you'll have a good idea of how the zip operation works.

##Exercise 21: Combine videos and bookmarks by index

Use a for loop to traverse the videos and bookmarks array at the same time. For each video and bookmark pair, create a {videoId, bookmarkId} pair and add it to the videoIdAndBookmarkIdPairs array.
```javascript
function() {
	var videos = [
			{
				"id": 70111470,
				"title": "Die Hard",
				"boxart": "http://cdn-0.nflximg.com/images/2891/DieHard.jpg",
				"uri": "http://api.netflix.com/catalog/titles/movies/70111470",
				"rating": 4.0,
			},
			{
				"id": 654356453,
				"title": "Bad Boys",
				"boxart": "http://cdn-0.nflximg.com/images/2891/BadBoys.jpg",
				"uri": "http://api.netflix.com/catalog/titles/movies/70111470",
				"rating": 5.0,
			},
			{
				"id": 65432445,
				"title": "The Chamber",
				"boxart": "http://cdn-0.nflximg.com/images/2891/TheChamber.jpg",
				"uri": "http://api.netflix.com/catalog/titles/movies/70111470",
				"rating": 4.0,
			},
			{
				"id": 675465,
				"title": "Fracture",
				"boxart": "http://cdn-0.nflximg.com/images/2891/Fracture.jpg",
				"uri": "http://api.netflix.com/catalog/titles/movies/70111470",
				"rating": 5.0,
			}
		],
		bookmarks = [
			{id: 470, time: 23432},
			{id: 453, time: 234324},
			{id: 445, time: 987834}
		],
	counter,
	videoIdAndBookmarkIdPairs = [];

	for(counter = 0; counter < Math.min(videos.length, bookmarks.length); counter++) {
		// Insert code here to create a {videoId, bookmarkId} pair and add it to the videoIdAndBookmarkIdPairs array.
	}

	return videoIdAndBookmarkIdPairs;
}
```

```javascript
function() {
	var videos = [{
			"id": 70111470,
			"title": "Die Hard",
			"boxart": "http://cdn-0.nflximg.com/images/2891/DieHard.jpg",
			"uri": "http://api.netflix.com/catalog/titles/movies/70111470",
			"rating": 4.0,
		}, {
			"id": 654356453,
			"title": "Bad Boys",
			"boxart": "http://cdn-0.nflximg.com/images/2891/BadBoys.jpg",
			"uri": "http://api.netflix.com/catalog/titles/movies/70111470",
			"rating": 5.0,
		}, {
			"id": 65432445,
			"title": "The Chamber",
			"boxart": "http://cdn-0.nflximg.com/images/2891/TheChamber.jpg",
			"uri": "http://api.netflix.com/catalog/titles/movies/70111470",
			"rating": 4.0,
		}, {
			"id": 675465,
			"title": "Fracture",
			"boxart": "http://cdn-0.nflximg.com/images/2891/Fracture.jpg",
			"uri": "http://api.netflix.com/catalog/titles/movies/70111470",
			"rating": 5.0,
		}],
		bookmarks = [{
			id: 470,
			time: 23432
		}, {
			id: 453,
			time: 234324
		}, {
			id: 445,
			time: 987834
		}],
		counter,
		videoIdAndBookmarkIdPairs = [];

	for (counter = 0; counter < Math.min(videos.length, bookmarks.length); counter++) {
		// Insert code here to create a {videoId, bookmarkId} pair and add it to the videoIdAndBookmarkIdPairs array.
		videoIdAndBookmarkIdPairs.push({
			videoId: videos[counter].id,
			bookmarkId: bookmarks[counter].id
		});
	}

	return videoIdAndBookmarkIdPairs;
}
```
##Exercise 22: Implement zip

Let's add a static zip() function to the Array type. The zip function accepts a combiner function, traverses each array at the same time, and calls the combiner function on the current item on the left-hand-side and right-hand-side. The zip function requires an item from each array in order to call the combiner function, therefore the array returned by zip will only be as large as the smallest input array.

```javascript
// JSON.stringify(Array.zip([1,2,3],[4,5,6], function(left, right) { return left + right })) === '[5,7,9]'

Array.zip = function(left, right, combinerFunction) {
	var counter,
		results = [];

	for(counter = 0; counter < Math.min(left.length, right.length); counter++) {
		// Add code here to apply the combinerFunction to the left and right-hand items in the respective arrays
	}

	return results;
};
```

```javascript
// JSON.stringify(Array.zip([1,2,3],[4,5,6], function(left, right) { return left + right })) === '[5,7,9]'

Array.zip = function(left, right, combinerFunction) {
	var counter,
		results = [];

	for (counter = 0; counter < Math.min(left.length, right.length); counter++) {
		// Add code here to apply the combinerFunction to the left and right-hand items in the respective arrays
		results.push(combinerFunction(left[counter], right[counter]));
	}

	return results;
};
```

##Exercise 23: Combine videos and bookmarks by index

Let's repeat exercise 21, but this time lets use your new zip() function. For each video and bookmark pair, create a {videoId, bookmarkId} pair.
```javascript
function() {
	var videos = [
			{
				"id": 70111470,
				"title": "Die Hard",
				"boxart": "http://cdn-0.nflximg.com/images/2891/DieHard.jpg",
				"uri": "http://api.netflix.com/catalog/titles/movies/70111470",
				"rating": 4.0,
			},
			{
				"id": 654356453,
				"title": "Bad Boys",
				"boxart": "http://cdn-0.nflximg.com/images/2891/BadBoys.jpg",
				"uri": "http://api.netflix.com/catalog/titles/movies/70111470",
				"rating": 5.0,
			},
			{
				"id": 65432445,
				"title": "The Chamber",
				"boxart": "http://cdn-0.nflximg.com/images/2891/TheChamber.jpg",
				"uri": "http://api.netflix.com/catalog/titles/movies/70111470",
				"rating": 4.0,
			},
			{
				"id": 675465,
				"title": "Fracture",
				"boxart": "http://cdn-0.nflximg.com/images/2891/Fracture.jpg",
				"uri": "http://api.netflix.com/catalog/titles/movies/70111470",
				"rating": 5.0,
			}
		],
		bookmarks = [
			{id: 470, time: 23432},
			{id: 453, time: 234324},
			{id: 445, time: 987834}
		];

	return Array.
		zip( //... finish this expression
}
```

```javascript
function() {
	var videos = [{
			"id": 70111470,
			"title": "Die Hard",
			"boxart": "http://cdn-0.nflximg.com/images/2891/DieHard.jpg",
			"uri": "http://api.netflix.com/catalog/titles/movies/70111470",
			"rating": 4.0,
		}, {
			"id": 654356453,
			"title": "Bad Boys",
			"boxart": "http://cdn-0.nflximg.com/images/2891/BadBoys.jpg",
			"uri": "http://api.netflix.com/catalog/titles/movies/70111470",
			"rating": 5.0,
		}, {
			"id": 65432445,
			"title": "The Chamber",
			"boxart": "http://cdn-0.nflximg.com/images/2891/TheChamber.jpg",
			"uri": "http://api.netflix.com/catalog/titles/movies/70111470",
			"rating": 4.0,
		}, {
			"id": 675465,
			"title": "Fracture",
			"boxart": "http://cdn-0.nflximg.com/images/2891/Fracture.jpg",
			"uri": "http://api.netflix.com/catalog/titles/movies/70111470",
			"rating": 5.0,
		}],
		bookmarks = [{
			id: 470,
			time: 23432
		}, {
			id: 453,
			time: 234324
		}, {
			id: 445,
			time: 987834
		}];

	return Array.
	zip(videos, bookmarks, (video, bookmark) => {
		return {
			videoId: video.id,
			bookmarkId: bookmark.id
		};
	}); //... finish this expression
}
```

## Exercise 24: Retrieve each video's id, title, middle interesting moment time, and smallest box art url.

This is a variation of the problem we solved earlier. This time each video has an interesting moments collection, each representing a time during which a screenshot is interesting or representative of the title as a whole. Notice that both the boxarts and interestingMoments arrays are located at the same depth in the tree. Retrieve the time of the middle interesting moment and the smallest box art url simultaneously with zip(). Return an {id, title, time, url} object for each video.

```javascript
function() {
	var movieLists = [
			{
				name: "New Releases",
				videos: [
					{
						"id": 70111470,
						"title": "Die Hard",
						"boxarts": [
							{ width: 150, height:200, url:"http://cdn-0.nflximg.com/images/2891/DieHard150.jpg" },
							{ width: 200, height:200, url:"http://cdn-0.nflximg.com/images/2891/DieHard200.jpg" }
						],
						"url": "http://api.netflix.com/catalog/titles/movies/70111470",
						"rating": 4.0,
						"interestingMoments": [
							{ type: "End", time:213432 },
							{ type: "Start", time: 64534 },
							{ type: "Middle", time: 323133}
						]
					},
					{
						"id": 654356453,
						"title": "Bad Boys",
						"boxarts": [
							{ width: 200, height:200, url:"http://cdn-0.nflximg.com/images/2891/BadBoys200.jpg" },
							{ width: 140, height:200, url:"http://cdn-0.nflximg.com/images/2891/BadBoys140.jpg" }

						],
						"url": "http://api.netflix.com/catalog/titles/movies/70111470",
						"rating": 5.0,
						"interestingMoments": [
							{ type: "End", time:54654754 },
							{ type: "Start", time: 43524243 },
							{ type: "Middle", time: 6575665}
						]
					}
				]
			},
			{
				name: "Instant Queue",
				videos: [
					{
						"id": 65432445,
						"title": "The Chamber",
						"boxarts": [
							{ width: 130, height:200, url:"http://cdn-0.nflximg.com/images/2891/TheChamber130.jpg" },
							{ width: 200, height:200, url:"http://cdn-0.nflximg.com/images/2891/TheChamber200.jpg" }
						],
						"url": "http://api.netflix.com/catalog/titles/movies/70111470",
						"rating": 4.0,
						"interestingMoments": [
							{ type: "End", time:132423 },
							{ type: "Start", time: 54637425 },
							{ type: "Middle", time: 3452343}
						]
					},
					{
						"id": 675465,
						"title": "Fracture",
						"boxarts": [
							{ width: 200, height:200, url:"http://cdn-0.nflximg.com/images/2891/Fracture200.jpg" },
							{ width: 120, height:200, url:"http://cdn-0.nflximg.com/images/2891/Fracture120.jpg" },
							{ width: 300, height:200, url:"http://cdn-0.nflximg.com/images/2891/Fracture300.jpg" }
						],
						"url": "http://api.netflix.com/catalog/titles/movies/70111470",
						"rating": 5.0,
						"interestingMoments": [
							{ type: "End", time:45632456 },
							{ type: "Start", time: 234534 },
							{ type: "Middle", time: 3453434}
						]
					}
				]
			}
		];

	//------------ COMPLETE THIS EXPRESSION --------------
	return movieLists.
		concatMap(function(movieList) {

		});

}
```
```javascript
function () {
    var movieLists = [{
        name: "New Releases",
        videos: [{
            "id": 70111470,
            "title": "Die Hard",
            "boxarts": [{
                width: 150,
                height: 200,
                url: "http://cdn-0.nflximg.com/images/2891/DieHard150.jpg"
            }, {
                width: 200,
                height: 200,
                url: "http://cdn-0.nflximg.com/images/2891/DieHard200.jpg"
            }],

            "url": "http://api.netflix.com/catalog/titles/movies/70111470",
            "rating": 4.0,
            "interestingMoments": [{
                type: "End",
                time: 213432
            }, {
                type: "Start",
                time: 64534
            }, {
                type: "Middle",
                time: 323133
            }]
        }, {
            "id": 654356453,
            "title": "Bad Boys",
            "boxarts": [{
                    width: 200,
                    height: 200,
                    url: "http://cdn-0.nflximg.com/images/2891/BadBoys200.jpg"
                }, {
                    width: 140,
                    height: 200,
                    url: "http://cdn-0.nflximg.com/images/2891/BadBoys140.jpg"
                }

            ],
            "url": "http://api.netflix.com/catalog/titles/movies/70111470",
            "rating": 5.0,
            "interestingMoments": [{
                type: "End",
                time: 54654754
            }, {
                type: "Start",
                time: 43524243
            }, {
                type: "Middle",
                time: 6575665
            }]
        }]
    }, {
        name: "Instant Queue",
        videos: [{
            "id": 65432445,
            "title": "The Chamber",
            "boxarts": [{
                width: 130,
                height: 200,
                url: "http://cdn-0.nflximg.com/images/2891/TheChamber130.jpg"
            }, {
                width: 200,
                height: 200,
                url: "http://cdn-0.nflximg.com/images/2891/TheChamber200.jpg"
            }],
            "url": "http://api.netflix.com/catalog/titles/movies/70111470",
            "rating": 4.0,
            "interestingMoments": [{
                type: "End",
                time: 132423
            }, {
                type: "Start",
                time: 54637425
            }, {
                type: "Middle",
                time: 3452343
            }]
        }, {
            "id": 675465,
            "title": "Fracture",
            "boxarts": [{
                width: 200,
                height: 200,
                url: "http://cdn-0.nflximg.com/images/2891/Fracture200.jpg"
            }, {
                width: 120,
                height: 200,
                url: "http://cdn-0.nflximg.com/images/2891/Fracture120.jpg"
            }, {
                width: 300,
                height: 200,
                url: "http://cdn-0.nflximg.com/images/2891/Fracture300.jpg"
            }],
            "url": "http://api.netflix.com/catalog/titles/movies/70111470",
            "rating": 5.0,
            "interestingMoments": [{
                type: "End",
                time: 45632456
            }, {
                type: "Start",
                time: 234534
            }, {
                type: "Middle",
                time: 3453434
            }]
        }]
    }];

    //------------ COMPLETE THIS EXPRESSION --------------
    return movieLists.concatMap(list => list.videos.concatMap(video =>
        Array.zip(
            video.boxarts.reduce((acc, curr) => acc.width * acc.height < curr.width * curr.height ? acc : curr),
            video.interestingMoments.filter(moment => moment.type === 'Middle'),
            (boxart, interestingMoment) => {
                return {
                    id: video.id,
                    title: video.title,
                    time: interestingMoment.time,
                    url: boxart.url
                };
            })
    ));
}
```

# Powerful Queries
Now that we've learned the five operators let's flex our muscles and write some powerful queries.

## Exercise 25: Converting from Arrays to Trees

When information is organized in a tree like a JSON expression, relationships point from parent to child. In relational systems like databases, relationships point from children to their parents. Both ways of organizing information are equivalent, and depending on the circumstances, we might get data organized in one way or another. It may surprise you to learn that you can use the 5 query functions you already know to easily convert between these representations. In other words, **not only can you query arrays from trees, you can query trees from arrays.**

We have 2 arrays each containing lists, and videos respectively. Each video has a listId field indicating its parent list. We want to build an array of list objects, each with a name and a videos array. The videos array will contain the video's id and title. In other words we want to build the following structure:
```javascript
[
	{
		"name": "New Releases",
		"videos": [
			{
				"id": 65432445,
				"title": "The Chamber"
			},
			{
				"id": 675465,
				"title": "Fracture"
			}
		]
	},
	{
		"name": "Thrillers",
		"videos": [
			{
				"id": 70111470,
				"title": "Die Hard"
			},
			{
				"id": 654356453,
				"title": "Bad Boys"
			}
		]
	}
]
```
**Note: please make sure when creating objects (both lists and videos) that you add properties in the same order as above. This doesn't impact the correctness of your code, but the verifier expects properties to be created in this order.**

```javascript
function () {
    var lists = [{
                "id": 5434364,
                "name": "New Releases"
            },
            {
                "id": 65456475,
                "name": "Thrillers"
            }
        ],
        videos = [{
                "listId": 5434364,
                "id": 65432445,
                "title": "The Chamber"
            },
            {
                "listId": 5434364,
                "id": 675465,
                "title": "Fracture"
            },
            {
                "listId": 65456475,
                "id": 70111470,
                "title": "Die Hard"
            },
            {
                "listId": 65456475,
                "id": 654356453,
                "title": "Bad Boys"
            }
        ];

    return lists. // complete this expression
}
```
```javascript
function () {
    var lists = [{
                "id": 5434364,
                "name": "New Releases"
            },
            {
                "id": 65456475,
                "name": "Thrillers"
            }
        ],
        videos = [{
                "listId": 5434364,
                "id": 65432445,
                "title": "The Chamber"
            },
            {
                "listId": 5434364,
                "id": 675465,
                "title": "Fracture"
            },
            {
                "listId": 65456475,
                "id": 70111470,
                "title": "Die Hard"
            },
            {
                "listId": 65456475,
                "id": 654356453,
                "title": "Bad Boys"
            }
        ];

    return lists.map(list => {
        return {
            name: list.name,
            videos: videos.filter(video => video.listId === list.id).map((video) => {
                return {
                    id: video.id,
                    title: video.title
                }
            })
        }
    }) // complete this expression
}
```
Looks like you figured out that you can use map and filter to *join* two different arrays by a key. Now let's try a more complex example...

## Exercise 26: Converting from Arrays to Deeper Trees

Let's try creating a deeper tree structure. This time we have 4 separate arrays each containing lists, videos, boxarts, and bookmarks respectively. Each object has a parent id, indicating its parent. We want to build an array of list objects, each with a name and a videos array. The videos array will contain the video's id, title, bookmark time, and smallest boxart url. In other words we want to build the following structure:
```javascript
[
	{
		"name": "New Releases",
		"videos": [
			{
				"id": 65432445,
				"title": "The Chamber",
				"time": 32432,
				"boxart": "http://cdn-0.nflximg.com/images/2891/TheChamber130.jpg"
			},
			{
				"id": 675465,
				"title": "Fracture",
				"time": 3534543,
				"boxart": "http://cdn-0.nflximg.com/images/2891/Fracture120.jpg"
			}
		]
	},
	{
		"name": "Thrillers",
		"videos": [
			{
				"id": 70111470,
				"title": "Die Hard",
				"time": 645243,
				"boxart": "http://cdn-0.nflximg.com/images/2891/DieHard150.jpg"
			},
			{
				"id": 654356453,
				"title": "Bad Boys",
				"time": 984934,
				"boxart": "http://cdn-0.nflximg.com/images/2891/BadBoys140.jpg"
			}
		]
	}
]
```
**Note: please make sure when creating objects (both lists and videos) that you add properties in the same order as above. This doesn't impact the correctness of your code, but the verifier expects properties to be created in this order.**

```javascript
function() {
	var lists = [
			{
				"id": 5434364,
				"name": "New Releases"
			},
			{
				"id": 65456475,
				name: "Thrillers"
			}
		],
		videos = [
			{
				"listId": 5434364,
				"id": 65432445,
				"title": "The Chamber"
			},
			{
				"listId": 5434364,
				"id": 675465,
				"title": "Fracture"
			},
			{
				"listId": 65456475,
				"id": 70111470,
				"title": "Die Hard"
			},
			{
				"listId": 65456475,
				"id": 654356453,
				"title": "Bad Boys"
			}
		],
		boxarts = [
			{ videoId: 65432445, width: 130, height:200, url:"http://cdn-0.nflximg.com/images/2891/TheChamber130.jpg" },
			{ videoId: 65432445, width: 200, height:200, url:"http://cdn-0.nflximg.com/images/2891/TheChamber200.jpg" },
			{ videoId: 675465, width: 200, height:200, url:"http://cdn-0.nflximg.com/images/2891/Fracture200.jpg" },
			{ videoId: 675465, width: 120, height:200, url:"http://cdn-0.nflximg.com/images/2891/Fracture120.jpg" },
			{ videoId: 675465, width: 300, height:200, url:"http://cdn-0.nflximg.com/images/2891/Fracture300.jpg" },
			{ videoId: 70111470, width: 150, height:200, url:"http://cdn-0.nflximg.com/images/2891/DieHard150.jpg" },
			{ videoId: 70111470, width: 200, height:200, url:"http://cdn-0.nflximg.com/images/2891/DieHard200.jpg" },
			{ videoId: 654356453, width: 200, height:200, url:"http://cdn-0.nflximg.com/images/2891/BadBoys200.jpg" },
			{ videoId: 654356453, width: 140, height:200, url:"http://cdn-0.nflximg.com/images/2891/BadBoys140.jpg" }
		],
		bookmarks = [
			{ videoId: 65432445, time: 32432 },
			{ videoId: 675465, time: 3534543 },
			{ videoId: 70111470, time: 645243 },
			{ videoId: 654356453, time: 984934 }
		];

	return list. // complete this expression

}
```
```javascript
function () {
    var lists = [{
                "id": 5434364,
                "name": "New Releases"
            },
            {
                "id": 65456475,
                name: "Thrillers"
            }
        ],
        videos = [{
                "listId": 5434364,
                "id": 65432445,
                "title": "The Chamber"
            },
            {
                "listId": 5434364,
                "id": 675465,
                "title": "Fracture"
            },
            {
                "listId": 65456475,
                "id": 70111470,
                "title": "Die Hard"
            },
            {
                "listId": 65456475,
                "id": 654356453,
                "title": "Bad Boys"
            }
        ],
        boxarts = [{
                videoId: 65432445,
                width: 130,
                height: 200,
                url: "http://cdn-0.nflximg.com/images/2891/TheChamber130.jpg"
            },
            {
                videoId: 65432445,
                width: 200,
                height: 200,
                url: "http://cdn-0.nflximg.com/images/2891/TheChamber200.jpg"
            },
            {
                videoId: 675465,
                width: 200,
                height: 200,
                url: "http://cdn-0.nflximg.com/images/2891/Fracture200.jpg"
            },
            {
                videoId: 675465,
                width: 120,
                height: 200,
                url: "http://cdn-0.nflximg.com/images/2891/Fracture120.jpg"
            },
            {
                videoId: 675465,
                width: 300,
                height: 200,
                url: "http://cdn-0.nflximg.com/images/2891/Fracture300.jpg"
            },
            {
                videoId: 70111470,
                width: 150,
                height: 200,
                url: "http://cdn-0.nflximg.com/images/2891/DieHard150.jpg"
            },
            {
                videoId: 70111470,
                width: 200,
                height: 200,
                url: "http://cdn-0.nflximg.com/images/2891/DieHard200.jpg"
            },
            {
                videoId: 654356453,
                width: 200,
                height: 200,
                url: "http://cdn-0.nflximg.com/images/2891/BadBoys200.jpg"
            },
            {
                videoId: 654356453,
                width: 140,
                height: 200,
                url: "http://cdn-0.nflximg.com/images/2891/BadBoys140.jpg"
            }
        ],
        bookmarks = [{
                videoId: 65432445,
                time: 32432
            },
            {
                videoId: 675465,
                time: 3534543
            },
            {
                videoId: 70111470,
                time: 645243
            },
            {
                videoId: 654356453,
                time: 984934
            }
        ];

    return lists.map(list => {
        return {
            name: list.name,
            videos: videos.filter(video => video.listId === list.id).concatMap(video =>
                Array.zip(bookmarks.filter(bookmark => bookmark.videoId === video.id),
                    boxarts.filter(boxart => boxart.videoId === video.id).reduce((acc, curr) => acc.width * acc.height < curr.width * curr.height ? acc : curr),
                    (bookmark, boxart) => {
                        return {
                            id: video.id,
                            title: video.title,
                            time: bookmark.time,
                            boxart: boxart.url
                        };
                    }
                )
            )
        }
    }) // complete this expression

}
```

Wow! That's a large query, but the code is still small relative to the amount of work it's doing. If we rewrote this query with a series of loops our code would be much less self-describing. Loops don't give the reader any information about the kind of operation being performed. Every time you see a loop, you need to carefully read through the code to find out what's being done. Is it a projection? A filter? A reduction? Why use loops for querying data when we've demonstrated that the 5 functions can be used to create virtually any output we want?

## Exercise 27: Stock Ticker

Let's try an easier question. Let's say we have a collection of all of the prices for NASDAQ stocks over time. Every time the price of a stock changes on the NASDAQ ticker an entry is added to this collection. Let's say that ten days ago you bought shares in Microsoft, and now you want to print all of the MSFT share prices since then. Filter the collection for MSFT trades starting from ten days ago and print each price record (including the time stamp) using the print() function. **Note: this is not a trick question. It's as easy as it seems.**
```javascript
// The pricesNASDAQ collection looks something like this...
var pricesNASDAQ = [
	// ... from the NASDAQ's opening day
	{name: "ANGI", price: 31.22, timeStamp: new Date(2011,11,15) },
	{name: "MSFT", price: 32.32, timeStamp: new Date(2011,11,15) },
	{name: "GOOG", price: 150.43, timeStamp: new Date(2011,11,15)},
	{name: "ANGI", price: 28.44, timeStamp: new Date(2011,11,16)},
	{name: "GOOG", price: 199.33, timeStamp: new Date(2011,11,16)},
	// ...and up to the present.
];
```

```javascript
function (pricesNASDAQ, printRecord) {
    var microsoftPrices,
        now = new Date(),
        tenDaysAgo = new Date(now.getFullYear(), now.getMonth(), now.getDate() - 10);

    // use filter() to filter the trades for MSFT prices recorded any time after 10 days ago
    microsoftPrices =
        pricesNASDAQ.
    filter(function (priceRecord) {
        return priceRecord.name === 'MSFT' && priceRecord.timeStamp > tenDaysAgo;
    }); 

    // Print the trades to the output console
    microsoftPrices.
    forEach(function (priceRecord) {
        printRecord(priceRecord);
    });
}
```
**Notice that the console is changing over time.** Now look at the time stamps on the stock prices. We're displaying stock prices sampled after we ran our program! How could our array have contained stock price records from the future? Did we accidentally rip a hole in the space-time continuum?

The solution to the riddle is that **pricesNASDAQ is `not` an array**. Unlike an array, which can only store a snapshot of stock prices, this new type can react to changes and update over time.

In the next section I'll reveal the inner workings of this magical type. You'll learn how you can use it to model everything from mouse events to asynchronous JSON requests. Finally I'll show you how **you can query this type using the 5 query functions you already know.** It's about time we gave this magical type a name...

# Working with Observables
Microsoft's open-source [Reactive Extensions](https://msdn.microsoft.com/library/hh242985.aspx) library introduces a new collection type to Javascript: **Observable**. An Observable is a lot like an Event. Like an Event, **an Observable is a sequence of values that a data producer *pushes* to the consumer**. However unlike an Event, **an Observable can signal to a listener that it has completed**, and will send no more data.

Observables can send data to consumers asynchronously. Unlike Array, there's no Javascript literal syntax for creating Observable sequences. However we can build a helper method that visually describes the contents of sequences as well as the times between each item's arrival. The **seq** function creates an Observable from an array of items, and adds a delay for every empty item encountered. Every ,,, adds up to a second.

```javascript
// An array of numbers 1,2,3
var numbers123Array =      [1,2,3];

// A sequence that returns 1, and then after 4 seconds returns 2,
// and then after another second returns 3, and then completes.
var numbers123Observable = seq([1,,,,,,,,,,,,2,,,3]);

// Like Arrays, Observables can contain any object - even Arrays.
var observableOfArrays = seq([ [1,2,3],,,,,,[4,5,6],,,,,,,,,,,[1,2] ]);
```
Observables are a sequence of values, delivered one after the other. Therefore it's possible that an Observable can go on sending data to a listener forever just like a mouse move event. To create a sequence that doesn't complete, you can add a trailing ,,, to the end of the items passed to seq().

```javascript
// The trailing ,,, ensures that the sequence will not complete.
var mouseMovesObservable =
	seq([ {x: 23, y: 55},,,,,,,{x: 44, y: 99},,,{x:55,y:99},,,{x: 54, y:543},,, ]);

// No trailing ,,, indicates that sequence will complete.
var numbers123Observable = seq([1,,,2,,,3]);
```
Querying Arrays only gives us a snapshot. By contrast, querying Observables allows us to create data sets that react and update as the system changes over time. This enables a very powerful type of programming known as reactive programming.

Let's start off by contrasting Observable with Events...

## Exercise 28: Subscribing to an event

You're probably used to thinking about events as a list of handlers stored in an object. In this example, we subscribe to a button click event and then unsubscribe the first time the button is clicked.

```javascript
function(button) {
	// the button click handler
	var handler = function(ev) {
		// Unsubscribe from the button event.
		button.removeEventListener("click", handler);

		alert("Button was clicked. Unsubscribing from event.");
	};

	// add the button click handler
	button.addEventListener("click", handler);
}
```
Ask yourself this question: **How is subscribing to an event different than traversing an array?** Both operations involve sending a listener a sequence of items by repeatedly invoking a function. So why can't we traverse Arrays and Events the same way?


##Exercise 29: Traversing an Event

Subscribing to an Event and traversing an Array are fundamentally the same operation. The only difference is that **Array traversal is synchronous and completes, and Event traversal is asynchronous and <u>never completes</u>**. If we convert a button click Event to an Observable object, we can use forEach() to traverse the Event.
```javascript
function(button) {
	var buttonClicks = Observable.fromEvent(button, "click");

	// In the case of an Observable, forEach returns a subscription object.
	var subscription =
		buttonClicks.
			forEach(function(clickEvent) {
				alert("Button was clicked. Stopping Traversal.");

				// Stop traversing the button clicks
				subscription.dispose();
			});
}
```
Notice that **Observable's forEach() function returns a Subscription object**. Disposing of a Subscription object unsubscribes from the event and prevents memory leaks. Disposing of a subscription is the asynchronous equivalent of stopping half-way through a counting for loop.

Disposing of a Subscription object is basically the same as calling removeEventListener(). On the surface, these two approaches to Event handling don't seem to be very different. Under the circumstances, why should we bother converting Events to Observables? The reason is that **if we convert Events to Observable Objects, we can use powerful functions to transform them.** In the next exercise we'll learn how we can use one such function to avoid dealing with Subscriptions in many cases...

## Exercise 30: Completing Sequences with take()

**Have you ever wished that you could listen for the next occurrence of an event and then immediately unsubscribe?** For example, developers will often attach an event handler to window.onload, expecting that their event handler will only be called once.

```javascript
window.addEventListener(
	"load",
	function()
		// do some work here, but expect this function will only be called once.
	})
```
In instances such as this, it's good practice to unsubscribe from the event after it's fired. Failing to unsubscribe is a **memory leak**. Depending on the circumstances, memory leaks can seriously destablize your application and can be very difficult to track down. Unfortunately unsubscribing from an event after one occurrence can be cumbersome:
```javascript
var handler = function() {
	// do some work here, then unsubscribe from the event
	window.removeEventListener("load", handler)
};
window.addEventListener("load", handler);
```
Wouldn't it be nice if there was an easier way to code this? That's why Observable has a take() function. The take() function works like this...
```javascript
seq([1,,,2,,,3,,,4,,,5,,,6,,,]).take(3) === seq([1,,,2,,,3]);
```
An Observable based on an Event will never complete on its own. The take() function creates a new sequence that completes after a discrete number of items arrive. This is important, because unlike an Event, *when an Observable sequence completes it unsubscribes all of its listeners*. That means that **if we use take() to complete our Event sequence, we don't need to unsubscribe!**

Let's repeat the previous exercise, in which we listened for a single button click and then unsubscribed. This time let's use the take() function to complete the sequence after the button is clicked.
```javascript
function(button) {
	var buttonClicks = Observable.fromEvent(button, "click");

	// Use take() to listen for only one button click
	// and unsubscribe.
	buttonClicks.
		// Insert take() call here
		forEach(function(clickEvent) {
			alert("Button was clicked once. Stopping Traversal.");
		});
}
```
```javascript
function(button) {
    var buttonClicks = Observable.fromEvent(button, "click");

    // Use take() to listen for only one button click
    // and unsubscribe.
    buttonClicks.
        take(1).
        // Insert take() call here
        forEach(function (clickEvent) {
            alert("Button was clicked once. Stopping Traversal.");
        });

}
```

The take() function is great way of listening for a discrete number of events and then unsubscribing, but Observable has an even *more* flexible function that we can use to complete sequences...

##Exercise 31: Completing sequences with takeUntil()

**Have you ever wanted to unsubscribe from one Event when another Event fires?** Observable's takeUntil() function is a convenient way of completing a sequence when another Event occurs. Here's how takeUntil() works:
```javascript
var numbersUntilStopButtonPressed =
	seq(              [ 1,,,2,,,3,,,4,,,5,,,6,,,7,,,8,,,9,,, ]).
		takeUntil(seq([  ,,, {eventType: "click"},,, ]) )                    === seq([ 1,,,2 ])
```
Earlier we (unknowningly) built a dynamic Microsoft price stock ticker using Observable. The problem with that stock ticker was that it *kept going on forever*. If left unchecked, all the entries in the log could use up all of the memory on the page. In the exercise below, filter the Observable sequence of NASDAQ prices for MSFT stock prices, use the fromEvent() function to create an Observable .
```javascript
function(pricesNASDAQ, printRecord, stopButton) {
	var stopButtonClicks = // ----- To finish this expression, use Observable.fromEvent to convert the "click" event on the stop button to an Observable
		microsoftPrices =
			pricesNASDAQ.
				filter(function(priceRecord) {
					return priceRecord.name === "MSFT";
				}).
				// ----- To finish this expression, use takeUntil to complete the sequence when stopButtonClicks fires.

	microsoftPrices.
		forEach(function(priceRecord) {
			printRecord(priceRecord);
		});
}
```
```javascript
function(pricesNASDAQ, printRecord, stopButton) {
    var stopButtonClicks = Observable.fromEvent(stopButton, "click"),// ----- To finish this expression, use Observable.fromEvent to convert the "click" event on the stop button to an Observable
        microsoftPrices =
            pricesNASDAQ.
                filter(function (priceRecord) {
                    return priceRecord.name === "MSFT";
                }).takeUntil(stopButtonClicks);
    // ----- To finish this expression, use takeUntil to complete the sequence when stopButtonClicks fires.

    microsoftPrices.
        forEach(function (priceRecord) {
            printRecord(priceRecord);
        });
}
```
We've learned that Observable sequences are much more powerful than raw events, because they can complete. **The take() and takeUntil() functions are powerful enough to ensure that we never have to unsubscribe from another event again!** This reduces the risk of memory leaks and makes our code more readable.
<br>
Here's what we learned in this section:
<br>

- We can traverse Observables using forEach().
- We can use fromEvent() to convert Events into Observables that never complete.
- We can apply take() and takeUntil() to an Observable to create a new sequence which *does* complete.
  <br>

In the next section we'll learn how to combine events to create more complex events. You'll be suprised how easily you can solve complex, asynchronous problems!

# Querying Observables
What's the difference between these two tasks?
<br>

- Creating a flat list of movies with a rating of 5.0 from a bunch of movie lists.
- Creating a sequence of all the mouse drag events from the mouseDown, mouseMove, and mouseUp events.

<br>
You might think of them as different, and might code them very differently, but **these tasks are fundamentally the same**. Both of these tasks are *queries*, and can be solved using the functions you've learned in these exercises.

**The difference between traversing an Array and traversing an Observable is *the direction in which the data moves***. When traversing an Array, the client pulls data from the data source, blocking until it gets a result. When traversing Observables, the data source pushes data at the client whenever it arrives.

It turns out that the direction in which data moves is *orthogonal* to querying that data. In other words, **when we're querying data it doesn't matter whether we pull data, or data is pushed at us.** In either case the query methods make the same transformations. The only thing that changes is the input and output type respectively. If we filter an Array, we get a new Array. If we filter an Observable, we get a new Observable, and so on.

Take a look at how the query methods transform Observables and Arrays:
```javascript
// map()

[1,2,3].map(function(x) { return x + 1 })                       === [2,3,4]
seq([1,,,2,,,3]).map(function(x) { return x + 1})               === seq([2,,,3,,,4])
seq([1,,,2,,,3,,,]).map(function(x) { return x + 1 })           === seq([2,,,3,,,4,,,])

// filter()

[1,2,3].filter(function(x) { return x > 1; })                   === [2,3]
seq([1,,,2,,,3]).filter(function(x) { return x > 1; })          === seq([2,,,3])
seq([1,,,2,,,3,,,]).filter(function(x) { return x > 1; })       === seq([2,,,3,,,])

// concatAll()

[ [1, 2, 3], [4, 5, 6] ].concatAll()                             === [1,2,3,4,5,6]
seq([ seq([1,,,2,,,3]),,,seq([4,,,5,,,6]) ]).concatAll()         === seq([1,,,2,,,3,,,4,,,5,,,6])

// If a new sequence arrives before all the items
// from the previous sequence have arrived, no attempt
// to retrieve the new sequence's elements is made until
// the previous sequence has completed. As a result the
// order of elements in the sequence is preserved.
seq([
	seq([1,,,, ,2, ,3])
	,,,seq([,,4, ,5, ,,6]) ]).
	concatAll()                                                  === seq([1,,,,,2,,3,,4,,5,,,6])

// Notice that as long as at least one sequence being
// concatenated is incomplete, the concatenated sequence is also
// incomplete.
seq([
	seq([1,, ,,, ,,,2,,,3])
	,,,seq([4,,,5,,, ,,, ,,6,,,]) ]).
	concatAll()                                                  === seq([1,,,,,,,,2,,,3,4,,,5,,,,,,,,6,,,])

// reduce()

[ 1, 2, 3 ].reduce(sumFunction)                                 === [ 6 ]
seq([ 1,,,2,,,3 ]).reduce(sumFunction)                          === seq([,,,,,,6])

// Reduced sequences do not complete until the
// sequence does.
seq([ 1,,,2,,,3,,, ]).reduce(sumFunction)                       === seq([ ,,,,,,,,,])

// zip()

// In both Arrays and Observables, the zipped sequence
// completes as soon as either the left or right-hand
// side sequence completes.
Array.zip([1,2],[3,4,5], sumFunction)                           === [4,6]
Observable.zip(seq([1,,,2]),seq([3,,,4,,,5]), sumFunction)      === seq([4,,,6])

// take()
[1,2,3].take(2)                                                 === [1, 2]
seq([ 1,,,2,,,3 ]).take(2)                                      === seq([ 1,,,2 ])
seq([ 1,,,2,,,3,,, ]).take(2)                                   === seq([ 1,,,2 ])

// takeUntil()

// takeUntil works for Arrays, but it's not very useful
// because the result will always be an empty array.
[1,2,3].takeUntil([1])                                          === []

seq([1,,,2,,,3,,, ]).takeUntil(
seq([ ,,, ,,4 , ]))                                             === seq([ 1,,,2 ])

```
Remember when I [prohibited the use of array indexers](http://reactivex.io/learnrx/#indexers)? The reason for that restriction should now become clearer to you. Whereas the 5 functions can be used on *any* collection, indexers can only be used on collections that support random-access (like Array). If you avoid indexers and stick to the functions you've learned in this tutorial, you'll have a unified programming model for transforming any collection. Having a unified programming model makes it trivial to convert synchronous code to asynchronous code, a process which would otherwise be very difficult. As we've demonstrated, you don't need indexers to perform complex collection transformations.

Now that we've seen that we can query asychronous and synchronous data sources using the same programming model, let's use Observable and our query functions to create complex new events.

## Exercise 32: Creating a mouse drag event

Remember the exercise we solved earlier? The one in which we retrieved all the movies with a rating of 5.0 from an array of movie lists? If we were to describe the solution in pseudocode it might read something like this...

**"For every movie list, retrieve only those videos with a rating of 5.0"**
```javascript
var moviesWithHighRatings =
	movieLists.
		concatMap(function(movieList) {
			return movieList.videos.
				filter(function(video) {
					return video.rating === 5.0;
				});
		});
```
Now we're going to create a mouseDrag event for a DOM object. If we were to describe this problem as pseudocode it might read something like this...

**"For every ~~movie list~~ mouse down event on the sprite, retrieve only those ~~videos with a rating of 5.0~~ mouse move events that occur before the next mouse up event."**

```javascript
function(sprite, spriteContainer) {
    var spriteMouseDowns = Observable.fromEvent(sprite, "mousedown"),
        spriteContainerMouseMoves = Observable.fromEvent(spriteContainer, "mousemove"),
        spriteContainerMouseUps = Observable.fromEvent(spriteContainer, "mouseup"),
        spriteMouseDrags =
            // For every mouse down event on the sprite...
            spriteMouseDowns.
                // --------------------------------------------------------
                //					  INSERT CODE HERE
                // --------------------------------------------------------
                // Complete this expression...
                // For every mouse down event, return the mouse move event
                // sequence until a mouse up event occurs.

                // For each mouse drag event, move the sprite to the absolute page position.
                spriteMouseDrags.forEach(function (dragPoint) {
                    sprite.style.left = dragPoint.pageX + "px";
                    sprite.style.top = dragPoint.pageY + "px";
                });
}

```
```javascript
function(sprite, spriteContainer) {
	var spriteMouseDowns = Observable.fromEvent(sprite, "mousedown"),
		spriteContainerMouseMoves = Observable.fromEvent(spriteContainer, "mousemove"),
		spriteContainerMouseUps = Observable.fromEvent(spriteContainer, "mouseup"),
		spriteMouseDrags =
			// For every mouse down event on the sprite...
			spriteMouseDowns.
				concatMap(function(contactPoint) {
					// ...retrieve all the mouse move events on the sprite container...
					return spriteContainerMouseMoves.
						// ...until a mouse up event occurs.
						takeUntil(spriteContainerMouseUps);
				});

	// For each mouse drag event, move the sprite to the absolute page position.
	spriteMouseDrags.forEach(function(dragPoint) {
		sprite.style.left = dragPoint.pageX + "px";
		sprite.style.top = dragPoint.pageY + "px";
	});
}
```
对吗?

```javascript
function(sprite, spriteContainer) {
    var spriteMouseDowns = Observable.fromEvent(sprite, "mousedown"),
        spriteContainerMouseMoves = Observable.fromEvent(spriteContainer, "mousemove"),
        spriteContainerMouseUps = Observable.fromEvent(spriteContainer, "mouseup"),
        spriteMouseDrags =
            // For every mouse down event on the sprite...
            spriteMouseDowns.concatMap(_ => spriteContainerMouseMoves.takeUntil(spriteContainerMouseUps));
    // --------------------------------------------------------
    //					  INSERT CODE HERE
    // --------------------------------------------------------
    // Complete this expression...
    // For every mouse down event, return the mouse move event
    // sequence until a mouse up event occurs.

    // For each mouse drag event, move the sprite to the absolute page position.
    spriteMouseDrags.forEach(function (dragPoint) {
        sprite.style.left = dragPoint.pageX + "px";
        sprite.style.top = dragPoint.pageY + "px";
    });
}

```
Now we're really cooking. We just created a complex event with a few lines of code. We didn't have to deal with any subscriptions objects, or write any stateful code whatsoever. Let's try something a little harder.

##Exercise 33: Improving our mouse drag event

Our mouse drag event is a little *too* simple. Notice that when we drag around the sprite, it always positions itself at the top-left corner of the mouse. Ideally we'd like our drag event to offset its coordinates, based on where the mouse was when the mouse down event occurred. This will make our mouse drag more closely resemble moving a real object with our finger.

Let's see if you can adjust the coordinates in the mouse drag event, based on the mousedown location on the sprite. The mouse events are sequences, and they look something like this:
```javascript
spriteContainerMouseMoves =
	seq([ {x: 200, y: 400, layerX: 10, layerY: 15},,,{x: 210, y: 410, layerX: 20, layerY: 26},,, ])
```
Each item in the mouse event sequences contains an x, y value that represents that absolute location of the mouse event on the page. The moveSprite() function uses these coordinates to position the sprite. Each item in the sequence *also* contains a pair of layerX and layerY properties that indicate the position of the mouse event relative to the event target.
```javascript
function(sprite, spriteContainer) {
    // All of the mouse event sequences look like this:
    // seq([ {pageX: 22, pageY: 3423, layerX: 14, layerY: 22} ,,, ])
    var spriteMouseDowns = Observable.fromEvent(sprite, "mousedown"),
        spriteContainerMouseMoves = Observable.fromEvent(spriteContainer, "mousemove"),
        spriteContainerMouseUps = Observable.fromEvent(spriteContainer, "mouseup"),
        // Create a sequence that looks like this:
        // seq([ {pageX: 22, pageY:4080 },,,{pageX: 24, pageY: 4082},,, ])
        spriteMouseDrags =
            // For every mouse down event on the sprite...
            spriteMouseDowns.
                concatMap(function (contactPoint) {
                    // ...retrieve all the mouse move events on the sprite container...
                    return spriteContainerMouseMoves.
                        // ...until a mouse up event occurs.
                        takeUntil(spriteContainerMouseUps).
						// ------------   INSERT CODE HERE  -----------------
						// Project each mouse move object into a new object
						// with adjusted pageX and pageY properties.
						// Translate each page coordinate based on the value
						// of the layerX and layerY properties in the
						// contactPoint.
						// -------------------------------------------------
						// Complete expression...
				});

    // For each mouse drag event, move the sprite to the absolute page position.
    spriteMouseDrags.forEach(function (dragPoint) {
        sprite.style.left = dragPoint.pageX + "px";
        sprite.style.top = dragPoint.pageY + "px";
    });
}
```
```javascript
function(sprite, spriteContainer) {
    // All of the mouse event sequences look like this:
    // seq([ {pageX: 22, pageY: 3423, layerX: 14, layerY: 22} ,,, ])
    var spriteMouseDowns = Observable.fromEvent(sprite, "mousedown"),
        spriteContainerMouseMoves = Observable.fromEvent(spriteContainer, "mousemove"),
        spriteContainerMouseUps = Observable.fromEvent(spriteContainer, "mouseup"),
        // Create a sequence that looks like this:
        // seq([ {pageX: 22, pageY:4080 },,,{pageX: 24, pageY: 4082},,, ])
        spriteMouseDrags =
            // For every mouse down event on the sprite...
            spriteMouseDowns.
                concatMap(concatPoint => spriteContainerMouseMoves
                    .takeUntil(spriteContainerMouseUps)
                    .map(movePoint => {
                        return {
                            pageX: movePoint.pageX - concatPoint.layerX,
                            pageY: movePoint.pageY - concatPoint.layerY,
                        };
                    }));


    // For each mouse drag event, move the sprite to the absolute page position.
    spriteMouseDrags.forEach(function (dragPoint) {
        sprite.style.left = dragPoint.pageX + "px";
        sprite.style.top = dragPoint.pageY + "px";
    });
}

```
## Exercise 34: HTTP requests

Events aren't the only source of asynchronous data in an application. There's also HTTP requests. Most of the time HTTP requests are exposed via a **callback-based API**. To receive data asynchronously from a callback-based API, the client typically passes a success and error handler to the function. When the asynchronous operation completes, the appropriate handler is called with the data. In this exercise we'll use jQuery's getJSON api to asynchronously retrieve data.
```javascript
function($) {
	$.getJSON(
		"http://api-global.netflix.com/queue",
		{
			success: function(json) {
				alert("Data has arrived.");
			},
			error: function(ex) {
				alert("There was an error.")
			}
		});
}
```
##Exercise 35: Sequencing HTTP requests with callbacks

Let's say that we're writing the startup flow for a web application. On startup, the application must perform the following operations:

1. Download the URL prefix to use for all subsequent AJAX calls. This URL prefix will vary based on what AB test the user is enrolled in.
2. Use the url prefix to do the following actions in parallel:
    - Retrieve a movie list array
    - Retr-eve configuration information and...
        - make a follow up call for an instant queue list if the config property "showInstantQueue" is truthy
3. If an instant queue list was retrieved, append it to the end of movie list.
4. If all operations were successful then display the movie lists *after* the window loads. Otherwise inform the user that there was a connectivity error.

```javascript
function(window, $, showMovieLists, showError) {
	var error,
		configDone,
		movieLists,
		queueList,
		windowLoaded,
		outputDisplayed,
		errorHandler = function() {
			// Otherwise show the error.
			error = "There was a connectivity error";

			// We may be ready to display out
			tryToDisplayOutput();
		},
		tryToDisplayOutput = function() {
			if (outputDisplayed) {
				return;
			}
			if (windowLoaded) {
				if (configDone && movieLists !== undefined) {
					if (queueList !== undefined) {
						movieLists.push(queueList);
					}
					outputDisplayed = true;
					showMovieLists(JSON.stringify(movieLists));
				}
				else if (error) {
					outputDisplayed = true;
					showError(error);
				}
			}
		},
		windowLoadHandler = function() {
			windowLoaded = true;

			// Remember to unsubscribe from events
			window.removeEventListener("load", windowLoadHandler);

			// This may be the last task we're waiting on, so try and display output.
			tryToDisplayOutput();
		};

	// Register for the load event
	window.addEventListener("load", windowLoadHandler);

	// Request the service url prefix for the users AB test
	$.getJSON(
		"http://api-global.netflix.com/abTestInformation",
		{
			success: function(abTestInformation) {
				// Request the member's config information to determine whether their instant
				// queue should be displayed.
				$.getJSON(
					"http://api-global.netflix.com/" + abTestInformation.urlPrefix + "/config",
					{
						success: function(config) {
							// Parallel retrieval of movie list could've failed,
							// in which case we don't want to issue this call.
							if (!error) {
								// If we're supposed to
								if (config.showInstantQueue) {
									$.getJSON(
										"http://api-global.netflix.com/" + abTestInformation.urlPrefix + "/queue",
										{
											success: function(queueMessage) {
												queueList = queueMessage.list;

												configDone = true;
												tryToDisplayOutput();
											},
											error: errorHandler
										});
								}
								else {
									configDone = true;
									tryToDisplayOutput();
								}
							}
						},
						error: errorHandler
					});

				// Retrieve the movie list
				$.getJSON(
					"http://api-global.netflix.com/" + abTestInformation.urlPrefix + "/movieLists",
					{
						success: function(movieListMessage) {
							movieLists = movieListMessage.list;
							tryToDisplayOutput();
						},
						error: errorHandler
					});
			},
			error: errorHandler
		});
}
```
It's fair to say that **sequencing HTTP requests with callbacks is *very* hard**. In order to perform two tasks in parallel, we have to introduce a variable to track the status of each task. Every time one of the parallel tasks completes it must check whether its sibling task has also completed. If both have completed, only then can we move forward. In the example above, every time a task is finished the tryToDisplayOutput() function is called to check if the program was ready to display output. This function checks the status of all tasks and displays the output if possible.

With a callback-based API, asynchronous error handling is also very complicated. In synchronous programs, a unit of work is cancelled when an exception is thrown. By contrast, in our program we had to explicitly track whether an error occurred in parallel to prevent an unnecessary call for the instant queue. Javascript provides us with special support for synchronous error handling with the keywords try/catch/throw. Unfortunately no such support is available for asynchronous programs.

The Observable interface is a much more powerful way of working with asynchronous APIs than callbacks. We'll see that Observables can free us from having to track the status of tasks that are run in parallel, just as Observables free us from having to track Event Subscriptions. We'll also see that Observable gives us the same error propagation semantics in asynchronous programs that we expect in synchronous programs. Finally we'll learn that by converting callback-based APIs to Observables, we can query them along with Events to build much more expressive programs.

## Exercise 36: Traversing callback-based Asynchronous APIs

**If a callback API were a sequence, what kind of sequence would it be?** We've seen that UI Event sequences can contain anywhere from 0 to infinite items, but will never complete on their own.
```javascript
mouseMoves === seq([ {x: 23, y: 55},,,,,,,{x: 44, y: 99},,,{x:55,y:99},,,{x: 54, y:543},,, ]);
```
In contrast, if we were to convert output from the $.getJSON() function we've been using into a sequence it would always return a sequence that completes after sending a single item.
```javascript
getJSONAsObservable("http://api-global.netflix.com/abTestInformation") ===
	seq([ { urlPrefix: "billboardTest" } ])
```
It might seem strange to create sequences that contain only one object. We *could* introduce an Observable-like type specifically for scalar values, but that would make callback-based APIs more difficult to query with Events. Thankfully, an Observable sequence is flexible enough to model both.

**So how do we convert a callback API into an Observable sequence?** Unfortunately, because callback-based APIs vary so much in their interfaces, we can't create a conversion function like we did with fromEvent(). However there is a more flexible function we can use to build Observable sequences...

**Observable.create() is powerful enough to convert any asynchronous API into an Observable.** Observable.create() relies on the fact that all asynchronous APIs have the following semantics:

The client needs to be able to receive data.
The client needs to be able to receive error information.
The client needs to be able to be alerted that the operation is complete.
The client needs to be able to indicate that they're no longer interested in the result of the operation.
In the following example, we'll use the Observable.create() function to create an Observable that issues a request to getJSON when it's traversed.
```javascript
function(window, $) {
	var getJSON = function(url) {
		return Observable.create(function(observer) {
			var subscribed = true;

			$.getJSON(url,
				{
					success:
						function(data) {
							// If client is still interested in the results, send them.
							if (subscribed) {
								// Send data to the client
								observer.next(data);
								// Immediately complete the sequence
								observer.complete();
							}
						},
					error: function(ex) {
						// If client is still interested in the results, send them.
						if (subscribed) {
							// Inform the client that an error occurred.
							observer.error(ex);
						}
					}
				});

			// Definition of the Subscription objects unsubscribe (dispose in RxJS 4) method.
			return function() {
				subscribed = false;
			}
		});
	};

	var observer = {
		// onNext in RxJS 4
		next: function (data) {
			alert(JSON.stringify(data));
		},
		// onError in RxJS 4
		error: function (err) {
			alert(err);
		},
		// onComplete in RxJS 4
		complete: function () {
			alert("The asynchronous operation has completed.");
		}
	};

	var subscription =
		getJSON("http://api-global.netflix.com/abTestInformation").subscribe(observer);

	// setTimeout(function () {
	// 	alert("Changed my mind, I do not want notifications any more!")
	// 	subscription.unsubscribe();
	// }, 10);
}
```
The argument passed into Observable.create() above is known as the subscribe function. Things that might be interested in data that the created Observable might produce (i.e. an Observer) can express this intention by subscribing to it. They must conform to the interface of an Observer in order for notifications pushed by the Observable to be delivered. Observers are then passed as an argument into the subscribe function of the created Observable.

Take note that the subscribe function defined for an Observable represents a lazy evaluation that only occurs for each Observer when it subscribes. Once an Observer no longer interested in the data an Observable has to provide, it should unsubscribe itself. The return value of calling subscribe on an Observable with some Observer is a Subscription, which represents a disposable resource. Calling unsubscribe on a Subscription object will clean up the Observable execution for the corresponding Observer.
<br>
Notice that the Observer above defines three methods:
<br>

- **next()**, used by Observables to deliver new data
- **error()**, used by Observables to deliver error information
- **complete()**, used by Observables to indicate a data sequence has completed

Observers are not expected to implement all the methods above (i.e. they may be partial). For callbacks that are not provided, Observable execution still proceeds normally, except some types of notifications will be ignored.

Between RxJS 4 and 5, there are some slight API differences to be wary of that relate to the discussion here. Please consult this [migration](https://github.com/ReactiveX/rxjs/blob/master/MIGRATION.md) guide for a detailed list of changes.

Now that we've built a version of the getJSON function that returns an Observable sequence, let's use it to improve our solution to the previous exercise...

## Exercise 37: Sequencing HTTP requests with Observable

Let's use the getJSON function that returns Observables, and the Observable.fromEvent() to complete the exercise we completed earlier.
```javascript
function(window, getJSON, showMovieLists, showError) {
	var movieListsSequence =
		Observable.zip(
			getJSON("http://api-global.netflix.com/abTestInformation").
				concatMap(function(abTestInformation) {
					return Observable.zip(
						getJSON("http://api-global.netflix.com/" + abTestInformation.urlPrefix + "/config").
							concatMap(function(config) {
								if (config.showInstantQueue) {
									return getJSON("http://api-global.netflix.com/" + abTestInformation.urlPrefix + "/queue").
										map(function(queueMessage) {
											return queueMessage.list;
										});
								}
								else {
									return Observable.returnValue(undefined);
								}
							}),
						getJSON("http://api-global.netflix.com/" + abTestInformation.urlPrefix + "/movieLists"),
						function(queue, movieListsMessage) {
							var copyOfMovieLists = Object.create(movieListsMessage.list);
							if (queue !== undefined) {
								copyOfMovieLists.push(queue);
							}

							return copyOfMovieLists;
						});
				}),
			Observable.fromEvent(window, "load"),
			function(movieLists, loadEvent) {
				return movieLists;
			});

	movieListsSequence.
		forEach(
			function(movieLists) {
				showMovieLists(movieLists);
			},
			function(err) {
				showError(err);
			});
}
```
Almost every workflow in a web application starts with an event, continues with an HTTP request, and results in a state change. Now we know how to express the first two tasks elegantly.

## Exercise 38: Throttle Input

When dealing with user input, there will be times when the user's input is too noisy, and will potentially clog your servers with extraneous requests. We want the ability to throttle the users's input so that if they interacting for one second, then we will get the user input. Let's say for example, the user clicks a button once too many times upon saving and we only want to fire after they've stopped for a second.

```
seq([1,2,3,,,,,,,4,5,6,,,]).throttleTime(1000 /* ms */) === seq([,,,,,,,3,,,,,,,,,,6,,,]);
```

```javascript
function (clicks, saveData, name) {
	return clicks.
		// TODO: Throttle the clicks so that it only happens every one second
		concatMap(function () {
			return saveData(name);
		});
}
```
Almost every workflow in a web application starts with an event, continues with an HTTP request, and results in a state change. Now we know how to express the first two tasks elegantly.

## Exercise 38: Throttle Input

When dealing with user input, there will be times when the user's input is too noisy, and will potentially clog your servers with extraneous requests. We want the ability to throttle the users's input so that if they interacting for one second, then we will get the user input. Let's say for example, the user clicks a button once too many times upon saving and we only want to fire after they've stopped for a second.
```javascript
seq([1,2,3,,,,,,,4,5,6,,,]).throttleTime(1000 /* ms */) === seq([,,,,,,,3,,,,,,,,,,6,,,]);
```

```javascript
function (clicks, saveData, name) {
	return clicks.
		// TODO: Throttle the clicks so that it only happens every one second
		concatMap(function () {
			return saveData(name);
		});
}
```
```javascript
function (clicks, saveData, name) {
    return clicks.
        throttleTime(1000).
        // TODO: Throttle the clicks so that it only happens every one second
        concatMap(function () {
            return saveData(name);
        });
}
```
Now that we know how to throttle input, let's take a look at another problem where throttling data is important...

## Exercise 39: Autocomplete Box

One of the most common problems in web development is the autocomplete box. This seems like it should be an easy problem, but is actually quite challenging. For example, how do we throttle the input? How do we make sure we're not getting out of order requests coming back? For example if I type "react" then type "reactive" I want "reactive" to be my result, regardless of which actually returned first from the service.

In the example below, you will be receiving a sequence of key presses, a textbox, and a function when called returns an array of search results.

```javascript
getSearchResultSet('react') === seq[,,,["reactive", "reaction","reactor"]]
keyPresses === seq['r',,,,,'e',,,,,,'a',,,,'c',,,,'t',,,,,]
```
```javascript
function (getSearchResultSet, keyPresses, textBox) {

	var getSearchResultSets =
		keyPresses.
		map(function () {
			return textBox.value;
		}).
		// TODO: Ensure that we only trigger a maximum of one search request per second
		concatMap(function (text) {

		// TODO: Ensure this sequence ends as soon as another key press arrives
		return getSearchResultSet(text);
	});

	return getSearchResultSets;
}
```

```javascript
function (getSearchResultSet, keyPresses, textBox) {

    var getSearchResultSets =
        keyPresses.
            map(function () {
                return textBox.value;
            }).
            // TODO: Ensure that we only trigger a maximum of one search request per second
            throttleTime(1000)
            .concatMap(function (text) {

                // TODO: Ensure this sequence ends as soon as another key press arrives
                return getSearchResultSet(text)
                    .takeUntil(keyPresses);
            });

    return getSearchResultSets;
}
```
Now that we're able to query with our throttled input, you'll still notice one slight problem. If you hit your arrow keys or any other non character key, the request will still fire. How do we prevent that?

## Exercise 40: Distinct Until Changed Input

You'll notice in the previous exercise that if you pressed your arrow keys while inside the textbox, the query will still fire, regardless of whether the text actually changed or not. How do we prevent that? The distinctUntilChanged filters out successive repetitive values.

```javascript
seq([1,,,1,,,3,,,3,,,5,,,1,,,]).distinctUntilChanged() ===
seq([1,,,,,,,3,,,,,,,5,,,1,,,]);
```
```javascript
javascriptfunction (keyPresses, isAlpha) {

	return keyPresses.
		map(function (e) { return String.fromCharCode(e.keyCode); }).

		// Ensure we only have alphabetic characters
		filter(function (character) { return isAlpha(character); }).

		// TODO: Filter out successive repetitive keys

		// Building up a string of all the characters typed.
		scan(function (stringSoFar, character) {
			return stringSoFar + character;
		}, '');
}
```
```javascript
function (keyPresses, isAlpha) {

	return keyPresses.
		map(function (e) { return String.fromCharCode(e.keyCode); }).
		filter(function (character) { return isAlpha(character); }).
		distinctUntilChanged().
		scan(function (stringSoFar, character) {
			return stringSoFar + character;
		}, '');
}
```
Now that we know how to get only the distinct input, let's see how it applies to our autocomplete example...

## Exercise 41: Autocomplete Box Part 2: Electric Boogaloo

In the previous version of the autocomplete box, there were two bugs

- Multiple successive searches are made for the same string
- Attempts are made to retrieve results for an empty string.

The example below is the same as above, but this time, fix the bugs!
```javascript
getSearchResultSet('react') === seq[,,,["reactive", "reaction","reactor"]]
keyPresses === seq['r',,,,,'e',,,,,,'a',,,,'c',,,,'t',,,,,]
```
```javascript
function (getSearchResultSet, keyPresses, textBox) {

	var getSearchResultSets =
		keyPresses.
			map(function () {
				return textBox.value;
			}).
			throttleTime(1000).

			// TODO: Make sure we only get distinct values

			// TODO: Make sure the text is not empty

			concatMap(function (text) {
				return getSearchResultSet(text).takeUntil(keyPresses);
			});

	return getSearchResultSets;
}
```

```javascript
function (getSearchResultSet, keyPresses, textBox) {

    var getSearchResultSets =
        keyPresses.
            map(function () {
                return textBox.value;
            }).
            throttleTime(1000).
            distinctUntilChanged().
            // TODO: Make sure we only get distinct values
            filter(function (text) {
                return !!text;
            }).
            // TODO: Make sure the text is not empty

            concatMap(function (text) {
                return getSearchResultSet(text).takeUntil(keyPresses);
            });

    return getSearchResultSets;
}
```
With just this little amount of code, we're able to produce a fully functioning autocomplete scenario. But there are other outstanding questions, such as error handling. How can we handle failure and retry if necessary?

## Exercise 42: Retrying after errors

A Work in Progress
Congratulations! You've made it this far, but you're not done. Learning is an on-going process. Go out and start using the functions you've learned in your day-to-day coding. Over time, I'll be adding more exercises to this tutorial. If you have suggestions for more exercises, send me a pull request!
​		