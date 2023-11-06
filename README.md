# Text Processor README

## URL
[Text Compression App](https://sumirr.github.io/flutter-text-compress/)


## Purpose
Takes a flutter ui file that extends multiple lines, and removes whitespaces to enable the user to parse the file to gpt.

## Description

This HTML file contains a Text Processor web application deployed on GitHub Pages. The application allows users to perform the following tasks:

- Enter text in the provided text area.
- Click the "Process Text" button to process the input text.
- View the processed text in two separate text areas, with the option to set a character limit for the first part of the text.
- Display word and character counts for both the first and second parts of the processed text.

The web application uses JavaScript and Bootstrap for its functionality and styling. 

## Example

### Compressed

```dart
import'package:flutter/material.dart';classCourseProgressWidgetextendsStatelessWidget{finalString?lessonTitle;finalintcompletedModules;finalintallLessons;CourseProgressWidget({Key?key,this.lessonTitle,requiredthis.completedModules,requiredthis.allLessons,}):super(key:key);@overrideWidgetbuild(BuildContextcontext){returnContainer(margin:EdgeInsets.only(left:8,right:8,top:8),padding:EdgeInsets.all(16),width:double.infinity,decoration:BoxDecoration(color:Colors.white,borderRadius:BorderRadius.circular(15),),child:Column(crossAxisAlignment:CrossAxisAlignment.start,children:[Text(lessonTitle??'',style:TextStyle(fontSize:20,fontWeight:FontWeight.bold,),),SizedBox(height:10),Row(children:[Expanded(child:LinearProgressIndicator(backgroundColor:Colors.grey[200],//setthebackgroundcolorvalueColor:AlwaysStoppedAnimation<Color>(Colors.green),//setthevaluecolorvalue:completedModules/(allLessons!=0?allLessons:1),),),SizedBox(width:10),//AddedtoprovidesomespacingbetweentheprogressbarandtheiconIcon(Icons.more_vert),],),SizedBox(height:10),Text('${completedModules}/${allLessons}Lessonsarecompleted',textAlign:TextAlign.center),],),);}}
```

### Original File
```dart
import 'package:flutter/material.dart';

class CourseProgressWidget extends StatelessWidget {
  final String? lessonTitle;
  final int completedModules;
  final int allLessons;

  CourseProgressWidget({
    Key? key,
    this.lessonTitle,
    required this.completedModules,
    required this.allLessons,
  }) : super(key: key);

  @override
  Widget build(BuildContext context) {
    return Container(
      margin: EdgeInsets.only(left: 8, right: 8, top: 8),
      padding: EdgeInsets.all(16),
      width: double.infinity,
      decoration: BoxDecoration(
        color: Colors.white,
        borderRadius: BorderRadius.circular(15),
      ),
      child: Column(
        crossAxisAlignment: CrossAxisAlignment.start,
        children: [
          Text(
            lessonTitle ?? '',
            style: TextStyle(
              fontSize: 20,
              fontWeight: FontWeight.bold,
            ),
          ),
          SizedBox(height: 10),
          Row(
            children: [
              Expanded(
                child: LinearProgressIndicator(
                  backgroundColor: Colors.grey[200], 
                  valueColor: AlwaysStoppedAnimation<Color>(
                      Colors.green), 
                  value: completedModules / (allLessons != 0 ? allLessons : 1),
                ),
              ),
              SizedBox(
                  width:
                      10), 
              Icon(Icons.more_vert),
            ],
          ),
          SizedBox(height: 10),
          Text('${completedModules} / ${allLessons} Lessons are completed',
              textAlign: TextAlign.center),
        ],
      ),
    );
  }
}

```
