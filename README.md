
# MaskedEditText

This project derives from [egslava/edittext-mask](https://github.com/egslava/edittext-mask), but it's been adapted for androidx and added support from [material-edit-text](https://github.com/rengwuxian/MaterialEditText) project for validation issues.

Enjoy!


*********************************
## en_US
MaskedEditText is a simple Android EditText with customizable input mask support.

For instance, you need user specified his phone in format +7(XXX)XXX-XX-XX. You also know user should have the only possibility to write digits but minuses, brackets and "+7" should appear automatically.

### Usage

Add this to your `build.gradle` :
```groovy
 implementation ('io.github.softmedtanzania:maskededittext:1.0.5')
```

Add _xmlns:mask="http://schemas.android.com/apk/res-auto"_ to your layout xml root:

      <io.github.softmedtanzania.MaskedEditText
        android:id="@+id/phone_input"
        android:layout_width="match_parent"
        android:layout_height="wrap_content"
        android:inputType="phone"
        android:typeface="monospace"
        mask:allowed_chars="1234567890"
        mask:mask="+7(###)###-##-##"
        android:hint="1234567890"
        app:keep_hint="true"
        />    
Where _mask_ is the input mask you want and '#' is an editable position (will be replaced by a whitespace on screen).

You can optionally set the representation character (in case you don't want to use '#'):

    <io.github.softmedtanzania.MaskedEditText
        android:layout_width="fill_parent"
        android:layout_height="wrap_content"
        mask:mask="ccc.ccc.ccc-cc"
        mask:char_representation="c"
    />

You can also change the mask and the representation character programatically:

	MaskedEditText editText = (MaskedEditText) findViewById(R.id.my_edit_text)
	// Setting the representation character to '$'
	editText.setCharRepresentation('$');
	// Logging the representation character
	Log.i("Representation character", editText.getCharRepresentation());
	// Setting the mask
	editText.setMask("##/##/####");
	// Logging the mask
	Log.i("Mask", editText.getMask());
	
To enable Enter softkey action (IME action):

	<io.github.softmedtanzania.MaskedEditText
	    ...
	    mask:enable_ime_action="true"
	    ...
	/>
    

Or programmatically:

	MaskedEditText editText = (MaskedEditText) findViewById(R.id.my_edit_text)
	editText.setImeActionEnabled(true);
	
*************************************************************************************************
