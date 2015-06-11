``nbgrader assign``
========================

::

    Produce the version of an assignment to be released to students.
    
    Options
    -------
    
    Arguments that take values are actually convenience aliases to full
    Configurables, whose aliases are listed on the help line. For more information
    on full configurables, see '--help-all'.
    
    --create
        Create an entry for the assignment in the database, if one does not already exist.
    --no-db
        Do not save information about grade cells into the database.
    --debug
        set log level to DEBUG (maximize logging output)
    --quiet
        set log level to CRITICAL (minimize logging output)
    --force
        Overwrite an assignment/submission if it already exists.
    --log-level=<Enum> (Application.log_level)
        Default: 30
        Choices: (0, 10, 20, 30, 40, 50, 'DEBUG', 'INFO', 'WARN', 'ERROR', 'CRITICAL')
        Set the log level by value or name.
    --db=<Unicode> (NbGraderConfig.db_url)
        Default: 'sqlite:///gradebook.db'
        URL to the database
    --course=<Unicode> (NbGraderConfig.course_id)
        Default: ''
        A key that is unique per instructor and course. This MUST be specified,
        either by setting the config option, or using the --course option on the
        command line.
    --config=<Unicode> (BasicConfig.extra_config_file)
        Default: ''
        Path to an extra config file to load. If specified, load this config file in
        addition to any other IPython config.
    --assignment=<Unicode> (NbGraderConfig.assignment_id)
        Default: ''
        The assignment name. This MUST be specified, either by setting the config
        option, passing an argument on the command line, or using the --assignment
        option on the command line.
    
    To see all available configurables, use `--help-all`
    
    Examples
    --------
    
        Produce the version of the assignment that is intended to be released to
        students. This performs several modifications to the original assignment:
        
            1. It inserts a header and/or footer to each notebook in the
               assignment, if the header/footer are specified.
        
            2. It locks certain cells so that they cannot be deleted by students
               accidentally (or on purpose!)
        
            3. It removes solutions from the notebooks and replaces them with
               code or text stubs saying (for example) "YOUR ANSWER HERE".
        
            4. It clears all outputs from the cells of the notebooks.
        
            5. It saves information about the cell contents so that we can warn
               students if they have changed the tests, or if they have failed
               to provide a response to a written answer. Specifically, this is
               done by computing a checksum of the cell contents and saving it
               into the cell metadata.
        
            6. It saves the tests used to grade students' code into a database,
               so that those tests can be replaced during autograding if they
               were modified by the student (you can prevent this by passing the
               --no-db flag).
        
               Additionally, the assignment must already be present in the
               database. To create it while running `nbgrader assign` if it
               doesn't already exist, pass the --create flag.
        
        `nbgrader assign` takes one argument (the name of the assignment), and
        looks for notebooks in the 'source' directory by default, according to
        the directory structure specified in `NbGraderConfig.directory_structure`.
        The student version is then saved into the 'release' directory.
        
        Note that the directory structure requires the `student_id` to be given;
        however, there is no student ID at this point in the process. Instead,
        `nbgrader assign` sets the student ID to be '.' so by default, files are
        read in according to:
        
            source/./{assignment_id}/{notebook_id}.ipynb
        
        and saved according to:
        
            release/./{assignment_id}/{notebook_id}.ipynb
    
    