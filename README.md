# Android_Bottom_Sheet
Creating Play store like purchase option a Bottom Sheet

# App Highlight

![Bottom Sheet Code](https://user-images.githubusercontent.com/74413402/192092276-1cb83e27-a2ec-42a7-890a-3ac4c3a8d57b.png)
![Bottom Sheet App](https://user-images.githubusercontent.com/74413402/192092278-f03eb067-fcdb-4b78-8b26-d9995df379f3.png)

# Code

**1. Create Fragment & Extent with BottomSheetDialogFragment**
```
public class BottomSheetFragment extends BottomSheetDialogFragment { ... }
```

#### MainActivity.java
```
        button.setOnClickListener(new View.OnClickListener() {
            @Override
            public void onClick(View v) {

                //call the bottom sheet fragment
                BottomSheetFragment bottomSheetFragment = new BottomSheetFragment();

                bottomSheetFragment.show(getSupportFragmentManager(), bottomSheetFragment.getTag());
            }
        });
```

### fragment_bottom_sheet.xml
``` 
<?xml version="1.0" encoding="utf-8"?>
<androidx.constraintlayout.widget.ConstraintLayout xmlns:android="http://schemas.android.com/apk/res/android"
    xmlns:app="http://schemas.android.com/apk/res-auto"
    xmlns:tools="http://schemas.android.com/tools"
    android:layout_width="match_parent"
    android:layout_height="wrap_content"
    tools:context=".Fragments.BottomSheetFragment">

    <TextView
        android:id="@+id/textView"
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:layout_marginStart="16dp"
        android:layout_marginTop="16dp"
        android:fontFamily="@font/roboto_medium"
        android:text="Order Details"
        android:textColor="@color/black"
        android:textSize="30sp"
        android:textStyle="bold"
        app:layout_constraintStart_toStartOf="parent"
        app:layout_constraintTop_toTopOf="parent" />

    <ImageView
        android:id="@+id/book1"
        android:layout_width="100dp"
        android:layout_height="100dp"
        android:layout_marginStart="8dp"
        android:layout_marginTop="16dp"
        android:scaleType="centerCrop"
        android:src="@drawable/book1"
        app:layout_constraintStart_toStartOf="parent"
        app:layout_constraintTop_toBottomOf="@+id/textView" />

    <TextView
        android:id="@+id/textView2"
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:layout_marginStart="16dp"
        android:fontFamily="@font/aclonica"
        android:text="Dark World"
        android:textColor="@color/black"
        app:layout_constraintBottom_toBottomOf="@+id/book1"
        app:layout_constraintStart_toEndOf="@+id/book1"
        app:layout_constraintTop_toTopOf="@+id/book1"
        app:layout_constraintVertical_bias="0.38" />

    <TextView
        android:id="@+id/textView3"
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:layout_marginStart="16dp"
        android:text="x1"
        app:layout_constraintStart_toEndOf="@+id/book1"
        app:layout_constraintTop_toBottomOf="@+id/textView2" />

    <TextView
        android:id="@+id/textView4"
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:layout_marginEnd="16dp"
        android:fontFamily="@font/roboto_medium"
        android:text="$50"
        android:textColor="@color/black"
        android:textSize="20sp"
        app:layout_constraintBottom_toBottomOf="@+id/book1"
        app:layout_constraintEnd_toEndOf="parent"
        app:layout_constraintTop_toTopOf="@+id/book1" />

    <ImageView
        android:id="@+id/book2"
        android:layout_width="100dp"
        android:layout_height="100dp"
        android:layout_marginStart="8dp"
        android:layout_marginTop="16dp"
        android:scaleType="centerCrop"
        android:src="@drawable/book2"
        app:layout_constraintStart_toStartOf="parent"
        app:layout_constraintTop_toBottomOf="@+id/book1" />

    <TextView
        android:id="@+id/textView5"
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:layout_marginStart="16dp"
        android:fontFamily="@font/aclonica"
        android:text="Dark World"
        android:textColor="@color/black"
        app:layout_constraintBottom_toBottomOf="@+id/book2"
        app:layout_constraintStart_toEndOf="@+id/book2"
        app:layout_constraintTop_toTopOf="@+id/book2"
        app:layout_constraintVertical_bias="0.38" />

    <TextView
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:layout_marginStart="16dp"
        android:text="x1"
        app:layout_constraintStart_toEndOf="@+id/book2"
        app:layout_constraintTop_toBottomOf="@+id/textView5" />

    <TextView
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:layout_marginEnd="16dp"
        android:fontFamily="@font/roboto_medium"
        android:text="$30"
        android:textColor="@color/black"
        android:textSize="20sp"
        app:layout_constraintBottom_toBottomOf="@+id/book2"
        app:layout_constraintEnd_toEndOf="parent"
        app:layout_constraintTop_toTopOf="@+id/book2" />

    <TextView
        android:id="@+id/textView6"
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:layout_marginTop="24dp"
        android:fontFamily="@font/roboto_medium"
        android:text="Total"
        android:textColor="@color/black"
        android:textSize="30sp"
        app:layout_constraintStart_toStartOf="@+id/book2"
        app:layout_constraintTop_toBottomOf="@+id/book2" />

    <TextView
        android:id="@+id/textView7"
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:text="With Packagin Charges"
        app:layout_constraintStart_toStartOf="@+id/textView6"
        app:layout_constraintTop_toBottomOf="@+id/textView6" />

    <TextView
        android:id="@+id/textView8"
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:layout_marginEnd="16dp"
        android:fontFamily="@font/roboto_medium"
        android:text="$80"
        android:textColor="@color/black"
        android:textSize="24sp"
        app:layout_constraintBottom_toBottomOf="@+id/textView7"
        app:layout_constraintEnd_toEndOf="parent"
        app:layout_constraintTop_toTopOf="@+id/textView6" />

    <androidx.appcompat.widget.AppCompatButton
        android:id="@+id/button"
        android:layout_width="0dp"
        android:layout_height="wrap_content"
        android:layout_marginTop="24dp"
        android:layout_marginBottom="8dp"
        android:background="#8BC34A"
        android:text="Purchase"
        android:textColor="@color/white"
        android:textSize="20sp"
        app:layout_constraintBottom_toBottomOf="parent"
        app:layout_constraintEnd_toEndOf="@+id/textView8"
        app:layout_constraintStart_toStartOf="@+id/textView6"
        app:layout_constraintTop_toBottomOf="@+id/textView7"
        tools:ignore="TextContrastCheck" />


</androidx.constraintlayout.widget.ConstraintLayout>
```

### Theme.xml 
**For Rounded Corner Theme**
```
<style>
    ...
    <item name="bottomSheetDialogTheme">@style/AppBottomSheetDialogTheme</item>

</style>
    
    <style name="AppBottomSheetDialogTheme"
        parent="Theme.Design.Light.BottomSheetDialog">
        <item name="bottomSheetStyle">@style/AppModalStyle</item>
    </style>

    <style name="AppModalStyle"
        parent="Widget.Design.BottomSheet.Modal">
        <item name="android:background">@drawable/bottomsheet_background</item>
```
