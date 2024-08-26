import maya.cmds as cmds

# Get the selected objects in Maya
selection = cmds.ls(sl=1)

if len(selection) == 0:
    print("Please select the objects in the scene.")
else:
    # Prompt user for suffix and prefix
    #user_suffix = input("Do you want a suffix? (yes or no): ").lower()
    #user_prefix = input("\nDo you want a prefix? (yes or no): ").lower()
    
    suffix = ""
    prefix = ""
    
    if user_prefix == "yes":
        prefix = input("\nEnter prefix: ")
    if user_suffix == "yes":
        suffix = input("\nEnter suffix: ")
            
    # Loop through each selected object and rename it
    for obj in selection:
        prefix1 = prefix
        suffix1 = suffix
        new_namep = ""
        renamed_obj = ""

        # Check if the object already has the prefix
        if obj.startswith(prefix):
            clean_prefix = input("\nDo you what to clean it prefix: Yes/No").lower()
            if clean_prefix == "yes":
                list = obj.split("_")
                n_name = list[1:]
                new_namep = "_".join(n_name)
                renamedp_obj = cmds.rename(obj, new_namep)
            else:
                prefix1 = ""
        # Check if the object already has the suffix
        if obj.endswith(suffix):
            clean_suffix = input("\nDo you what to clean it suffix: Yes/No").lower()
            if clean_suffix == "yes":
                list = new_namep.split("_")
                n_name = list[:-1]
                new_name = "_".join(n_name)
                renamed_obj = cmds.rename(renamedp_obj, new_name)
            else:    
                suffix1 = ""

        # Create new name with the prefix and suffix, handling underscores appropriately
        new_name = (prefix1 + "_" if prefix1 else "") + obj + ("_" + suffix1 if suffix1 else "")

        # Rename the object
        #renamed_obj = cmds.rename(obj, new_name)
        print(f"Renamed to: {renamed_obj}")
