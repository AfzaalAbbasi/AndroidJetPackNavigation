# AndroidJetPackNavigation
Android JetPack Navigation  Example for Begineers


To include Navigation support in your project, add the following dependencies to your app's build.gradle file:

    implementation 'androidx.navigation:navigation-fragment-ktx:2.2.2'
    implementation 'androidx.navigation:navigation-ui-ktx:2.2.2'
    
 # Create a navigation graph
 
 Navigation occurs between your app's destinations—that is, anywhere in your app to which users can navigate. These destinations are connected via actions.
A navigation graph is a resource file that contains all of your destinations and actions. The graph represents all of your app's navigation paths.

![image](https://user-images.githubusercontent.com/15030540/154850037-72c732c2-f19a-47f5-9593-681421f270ea.png)


To add a navigation graph to your project, do the following:

In the Project window, right-click on the res directory and select New > Android Resource File. The New Resource File dialog appears.
Type a name in the File name field, such as "nav_graph".
Select Navigation from the Resource type drop-down list, and then click OK.
When you add your first navigation graph, Android Studio creates a navigation resource directory within the res directory. This directory contains your navigation graph resource file (nav_graph.xml, for example).

# Add a NavHostFragment via XML:

In Activity xml Add following NavHostFragment

```
 <androidx.fragment.app.FragmentContainerView
        android:id="@+id/nav_host_fragment"
        android:name="androidx.navigation.fragment.NavHostFragment"
        android:layout_width="0dp"
        android:layout_height="0dp"
        app:defaultNavHost="true"
        app:layout_constraintBottom_toBottomOf="parent"
        app:layout_constraintLeft_toLeftOf="parent"
        app:layout_constraintRight_toRightOf="parent"
        app:layout_constraintTop_toTopOf="parent"
        app:navGraph="@navigation/nav_graph" />
  
```

 Inside Activity onCreate write following code.
  
  ```
         val navHostFragment = supportFragmentManager
            .findFragmentById(R.id.nav_host_fragment) as NavHostFragment
        navController = navHostFragment.navController

        // Set up the action bar for use with the NavController
        setupActionBarWithNavController(navController)
 ```
       
# Navigate to a destination:
There are multiple ways to navigate from one fragment to another using a ```NavController```, for instance

  ```
 findNavController().navigate(R.id.action_startFragment_to_firstFragment)
 
 
  ```


