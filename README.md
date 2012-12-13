StaggeredGridView
=======

## Introduction

This is a modified version of Android's experimental StaggeredGridView. The StaggeredGridView allows the user to create a GridView with uneven rows similar to how Pinterest looks. Includes own OnItemClickListener and OnItemLongClickListener, selector, and fixed position restore.

## Setup

To use StaggeredGridView in your projects, simply add this project to your workspace then add it as a library project to your current project. 

## Usage

StaggeredGridView can be added as a custom view to any layout. 

Attributes supported (same behavior as GridView): 
 * numColumns : determines the amount of columns to be drawn
 * drawSelectorOnTop : determine if selector should be drawn on top

```xml

<LinearLayout xmlns:android="http://schemas.android.com/apk/res/android"
    xmlns:tools="http://schemas.android.com/tools"
    xmlns:staggered="http://schemas.android.com/apk/res-auto"
    android:layout_width="match_parent"
    android:layout_height="match_parent"
    android:id="@+id/mainLayout">

    <com.origamilabs.library.views.StaggeredGridView
        android:id="@+id/staggeredGridView1"
        staggered:numColumns="2"
        staggered:drawSelectorOnTop="true"
        android:layout_width="match_parent"
        android:layout_height="wrap_content" />

</LinearLayout>
```
The StaggeredGridView includes its own interface's OnItemClickListener, and OnItemLongClickListener since StaggeredGridView does not extend an AdapterView. Behavior is the same.

```java

onItemClick(StaggeredGridView parent, View view, int position, long id);

onItemLongClick(StaggeredGridView parent, View view, int position, long id);
```

## Tests

No tests have been written however I have tested this View manually with 2.2.2+ devices. Please report any issues.


## TODO:

* implement more custom attributes to mirror GridView's attributes
* develop tests
* hideSelector()
* support multiple choice mode
* currently restoring position can result in the views to be slightly offset when user flings to the top. This is corrected by checking the offsets when position 0 is reached. Would like to dig deeper into the issue. 

