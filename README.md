# Ex.No:8 To create a gallery control using android studio to display images or photos.


## AIM:

To create a gallery control using android studio to display images or photos.

## EQUIPMENTS REQUIRED:

Latest Version Android Studio

## ALGORITHM:



## PROGRAM:
```
/*
Program to print the text “GalleryControl”.
Developed by:VISHVA V
Registeration Number :212222040182
*/
```
## In activity_main.xml :
```
<?xml version="1.0" encoding="utf-8"?>
<androidx.constraintlayout.widget.ConstraintLayout xmlns:android="http://schemas.android.com/apk/res/android"
    xmlns:app="http://schemas.android.com/apk/res-auto"
    xmlns:tools="http://schemas.android.com/tools"
    android:layout_width="match_parent"
    android:layout_height="match_parent"
    tools:context=".MainActivity">

    <Gallery
        android:id="@+id/gallery"
        android:layout_width="fill_parent"
        android:layout_height="wrap_content"
        android:layout_alignParentTop="true"
        android:layout_centerHorizontal="true"
        app:layout_constraintBottom_toBottomOf="parent"
        app:layout_constraintEnd_toEndOf="parent"
        app:layout_constraintHorizontal_bias="0.0"
        app:layout_constraintStart_toStartOf="parent"
        app:layout_constraintTop_toTopOf="parent"
        app:layout_constraintVertical_bias="0.889" />

    <ImageView
        android:id="@+id/imageView"
        android:layout_width="fill_parent"
        android:layout_height="fill_parent"
        android:layout_below="@+id/gallery"
        android:layout_centerHorizontal="true"
        android:scaleType="fitCenter"
        app:layout_constraintBottom_toBottomOf="@+id/gallery"
        app:layout_constraintStart_toEndOf="parent"
        app:layout_constraintTop_toTopOf="@+id/gallery"
        app:layout_constraintVertical_bias="0.849" />

    <TextView
        android:id="@+id/textView"
        android:layout_width="174dp"
        android:layout_height="99dp"
        android:text="Gallery Control"
        android:textAlignment="center"
        android:textSize="28sp"
        android:textStyle="bold|italic"
        app:layout_constraintBottom_toBottomOf="parent"
        app:layout_constraintEnd_toEndOf="parent"
        app:layout_constraintHorizontal_bias="0.498"
        app:layout_constraintStart_toStartOf="parent"
        app:layout_constraintTop_toTopOf="parent"
        app:layout_constraintVertical_bias="0.045" />

</androidx.constraintlayout.widget.ConstraintLayout>
```
## MainActivity.java :
```
package com.example.gallerycontrol;

import android.app.Activity;
import android.content.Context;
import android.os.Bundle;
import android.view.View;
import android.view.ViewGroup;
import android.widget.AdapterView;
import android.widget.BaseAdapter;
import android.widget.Gallery;
import android.widget.ImageView;

public class MainActivity extends Activity {

    private Integer[] mImageIds = {
            R.drawable.download,
            R.drawable.australiaflag,
            R.drawable.portugalflag,

    };

    @Override
    protected void onCreate(Bundle savedInstanceState) {
        super.onCreate(savedInstanceState);
        setContentView(R.layout.activity_main);

        Gallery gallery = (Gallery) findViewById(R.id.gallery);
        gallery.setAdapter(new ImageAdapter(this));

        gallery.setOnItemClickListener(new AdapterView.OnItemClickListener() {
            @Override
            public void onItemClick(AdapterView<?> parent, View view, int position, long id) {
                ImageView imageView = (ImageView) findViewById(R.id.imageView);
                imageView.setImageResource(mImageIds[position]);
            }
        });
    }

    public class ImageAdapter extends BaseAdapter {
        private Context mContext;

        public ImageAdapter(Context c) {
            mContext = c;
        }

        public int getCount() {
            return mImageIds.length;
        }

        public Object getItem(int position) {
            return null;
        }

        public long getItemId(int position) {
            return 0;
        }

        public View getView(int position, View convertView, ViewGroup parent) {
            ImageView imageView = new ImageView(mContext);
            imageView.setImageResource(mImageIds[position]);
            imageView.setLayoutParams(new Gallery.LayoutParams(150, 100));
            imageView.setScaleType(ImageView.ScaleType.FIT_XY);
            return imageView;
        }
    }
}
```


## OUTPUT
![Screenshot 2024-05-08 102721](https://github.com/VISHVA12300/gallerycontrol/assets/119404426/63326eb3-c716-44ab-9dd4-d4784f7131fe)

![Screenshot 2024-05-08 102733](https://github.com/VISHVA12300/gallerycontrol/assets/119404426/72a330c5-10d1-4ecd-8b9e-fae4a62550a8)
![Screenshot 2024-05-08 102741](https://github.com/VISHVA12300/gallerycontrol/assets/119404426/d9f56622-1632-4317-9edc-ed8e4ccb1c35)

## RESULT
Thus a Simple Android Application to create a gallery control using android studio to display images or photos is developed and executed successfully.

