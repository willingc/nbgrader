Configuration options
=====================

These options can be set in ``nbgrader_config.py``, or at the command line when you start it.
::

    # Configuration file for nbgrader.
    
    c = get_config()
    
    #------------------------------------------------------------------------------
    # NbGraderApp configuration
    #------------------------------------------------------------------------------
    
    # NbGraderApp will inherit config from: BaseNbGraderApp, BaseApp,
    # BaseIPythonApplication, Application
    
    # List of file names or file globs to be ignored when copying directories.
    # c.NbGraderApp.ignore = ['.ipynb_checkpoints', '*.pyc', '__pycache__']
    
    # Set the log level by value or name.
    # c.NbGraderApp.log_level = 30
    
    # Generate a new config file
    # c.NbGraderApp.generate_config = False
    
    #------------------------------------------------------------------------------
    # BasicConfig configuration
    #------------------------------------------------------------------------------
    
    # Config options that inherited from IPython.
    
    # Path to an extra config file to load. If specified, load this config file in
    # addition to any other IPython config.
    # c.BasicConfig.extra_config_file = ''
    
    # Whether to install the default config files into the profile dir. If a new
    # profile is being created, and IPython contains config files for that profile,
    # then they will be staged into the new directory. Otherwise, default config
    # files will be automatically generated.
    # c.BasicConfig.copy_config_files = False
    
    # Whether to overwrite existing config files when copying
    # c.BasicConfig.overwrite = False
    
    # Default IPython profile to use
    # c.BasicConfig.profile = 'nbgrader'
    
    # The name of the IPython directory. This directory is used for logging
    # configuration (through profiles), history storage, etc. The default is usually
    # $HOME/.ipython. This option can also be specified through the environment
    # variable IPYTHONDIR.
    # c.BasicConfig.ipython_dir = '/Users/jhamrick/.ipython'
    
    # The logging format template
    # c.BasicConfig.log_format = '%(color)s[%(name)s | %(levelname)s]%(end_color)s %(message)s'
    
    # Whether to automatically generate the profile
    # c.BasicConfig.auto_create = True
    
    # The date format used by logging formatters for %(asctime)s
    # c.BasicConfig.log_datefmt = '%Y-%m-%d %H:%M:%S'
    
    #------------------------------------------------------------------------------
    # NbGraderConfig configuration
    #------------------------------------------------------------------------------
    
    # Config options that are common across nbgrader apps
    
    # The name of the directory that contains the master/instructor version of
    # assignments. This corresponds to the `nbgrader_step` variable in the
    # `directory_structure` config option.
    # c.NbGraderConfig.source_directory = 'source'
    
    # File glob to match notebook names, excluding the '.ipynb' extension. This can
    # be changed to filter by notebook.
    # c.NbGraderConfig.notebook_id = '*'
    
    # The name of the directory that contains assignment feedback after grading has
    # been completed. This corresponds to the `nbgrader_step` variable in the
    # `directory_structure` config option.
    # c.NbGraderConfig.feedback_directory = 'feedback'
    
    # The name of the directory that contains assignments that have been submitted
    # by students for grading. This corresponds to the `nbgrader_step` variable in
    # the `directory_structure` config option.
    # c.NbGraderConfig.submitted_directory = 'submitted'
    
    # Format string for the directory structure that nbgrader works over during the
    # grading process. This MUST contain named keys for 'nbgrader_step',
    # 'student_id', and 'assignment_id'. It SHOULD NOT contain a key for
    # 'notebook_id', as this will be automatically joined with the rest of the path.
    # c.NbGraderConfig.directory_structure = '{nbgrader_step}/{student_id}/{assignment_id}'
    
    # URL to the database
    # c.NbGraderConfig.db_url = 'sqlite:///gradebook.db'
    
    # The name of the directory that contains assignment submissions after they have
    # been autograded. This corresponds to the `nbgrader_step` variable in the
    # `directory_structure` config option.
    # c.NbGraderConfig.autograded_directory = 'autograded'
    
    # The assignment name. This MUST be specified, either by setting the config
    # option, passing an argument on the command line, or using the --assignment
    # option on the command line.
    # c.NbGraderConfig.assignment_id = ''
    
    # A key that is unique per instructor and course. This MUST be specified, either
    # by setting the config option, or using the --course option on the command
    # line.
    # c.NbGraderConfig.course_id = ''
    
    # The name of the directory that contains the version of the assignment that
    # will be released to students. This corresponds to the `nbgrader_step` variable
    # in the `directory_structure` config option.
    # c.NbGraderConfig.release_directory = 'release'
    
    # File glob to match student IDs. This can be changed to filter by student.
    # Note: this is always changed to '.' when running `nbgrader assign`, as the
    # assign step doesn't have any student ID associated with it.
    # c.NbGraderConfig.student_id = '*'
    
    #------------------------------------------------------------------------------
    # CollectApp configuration
    #------------------------------------------------------------------------------
    
    # CollectApp will inherit config from: TransferApp, BaseNbGraderApp, BaseApp,
    # BaseIPythonApplication, Application
    
    # List of file names or file globs to be ignored when copying directories.
    # c.CollectApp.ignore = ['.ipynb_checkpoints', '*.pyc', '__pycache__']
    
    # The nbgrader exchange directory writable to everyone. MUST be preexisting.
    # c.CollectApp.exchange_directory = '/srv/nbgrader/exchange'
    
    # Timezone for recording timestamps
    # c.CollectApp.timezone = 'UTC'
    
    # Format string for timestamps
    # c.CollectApp.timestamp_format = '%Y-%m-%d %H:%M:%S %Z'
    
    # Set the log level by value or name.
    # c.CollectApp.log_level = 30
    
    # Update existing submissions with ones that have newer timestamps.
    # c.CollectApp.update = False
    
    #------------------------------------------------------------------------------
    # FormgradeApp configuration
    #------------------------------------------------------------------------------
    
    # FormgradeApp will inherit config from: BaseNbGraderApp, BaseApp,
    # BaseIPythonApplication, Application
    
    # Port for the server
    # c.FormgradeApp.port = 5000
    
    # List of file names or file globs to be ignored when copying directories.
    # c.FormgradeApp.ignore = ['.ipynb_checkpoints', '*.pyc', '__pycache__']
    
    # Authenticator used in all formgrade requests.
    # c.FormgradeApp.authenticator_class = <class 'nbgrader.auth.noauth.NoAuth'>
    
    # URL or local path to mathjax installation. To install it locally, install
    # mathjax with IPython and then configure this variable to use the local
    # version.
    # c.FormgradeApp.mathjax_url = ''
    
    # IP address for the server
    # c.FormgradeApp.ip = 'localhost'
    
    # Set the log level by value or name.
    # c.FormgradeApp.log_level = 30
    
    #------------------------------------------------------------------------------
    # FetchApp configuration
    #------------------------------------------------------------------------------
    
    # FetchApp will inherit config from: TransferApp, BaseNbGraderApp, BaseApp,
    # BaseIPythonApplication, Application
    
    # Timezone for recording timestamps
    # c.FetchApp.timezone = 'UTC'
    
    # List of file names or file globs to be ignored when copying directories.
    # c.FetchApp.ignore = ['.ipynb_checkpoints', '*.pyc', '__pycache__']
    
    # Set the log level by value or name.
    # c.FetchApp.log_level = 30
    
    # The nbgrader exchange directory writable to everyone. MUST be preexisting.
    # c.FetchApp.exchange_directory = '/srv/nbgrader/exchange'
    
    # Format string for timestamps
    # c.FetchApp.timestamp_format = '%Y-%m-%d %H:%M:%S %Z'
    
    #------------------------------------------------------------------------------
    # SubmitApp configuration
    #------------------------------------------------------------------------------
    
    # SubmitApp will inherit config from: TransferApp, BaseNbGraderApp, BaseApp,
    # BaseIPythonApplication, Application
    
    # Timezone for recording timestamps
    # c.SubmitApp.timezone = 'UTC'
    
    # List of file names or file globs to be ignored when copying directories.
    # c.SubmitApp.ignore = ['.ipynb_checkpoints', '*.pyc', '__pycache__']
    
    # Set the log level by value or name.
    # c.SubmitApp.log_level = 30
    
    # The nbgrader exchange directory writable to everyone. MUST be preexisting.
    # c.SubmitApp.exchange_directory = '/srv/nbgrader/exchange'
    
    # Format string for timestamps
    # c.SubmitApp.timestamp_format = '%Y-%m-%d %H:%M:%S %Z'
    
    #------------------------------------------------------------------------------
    # ExtensionApp configuration
    #------------------------------------------------------------------------------
    
    # ExtensionApp will inherit config from: Application
    
    # The Logging format template
    # c.ExtensionApp.log_format = '[%(name)s]%(highlevel)s %(message)s'
    
    # Set the log level by value or name.
    # c.ExtensionApp.log_level = 30
    
    # The date format used by logging formatters for %(asctime)s
    # c.ExtensionApp.log_datefmt = '%Y-%m-%d %H:%M:%S'
    
    #------------------------------------------------------------------------------
    # ListApp configuration
    #------------------------------------------------------------------------------
    
    # ListApp will inherit config from: TransferApp, BaseNbGraderApp, BaseApp,
    # BaseIPythonApplication, Application
    
    # List inbound files rather than outbound.
    # c.ListApp.inbound = False
    
    # Remove, rather than list files.
    # c.ListApp.remove = False
    
    # The nbgrader exchange directory writable to everyone. MUST be preexisting.
    # c.ListApp.exchange_directory = '/srv/nbgrader/exchange'
    
    # List of file names or file globs to be ignored when copying directories.
    # c.ListApp.ignore = ['.ipynb_checkpoints', '*.pyc', '__pycache__']
    
    # Timezone for recording timestamps
    # c.ListApp.timezone = 'UTC'
    
    # Format string for timestamps
    # c.ListApp.timestamp_format = '%Y-%m-%d %H:%M:%S %Z'
    
    # Set the log level by value or name.
    # c.ListApp.log_level = 30
    
    #------------------------------------------------------------------------------
    # FeedbackApp configuration
    #------------------------------------------------------------------------------
    
    # FeedbackApp will inherit config from: BaseNbConvertApp, BaseNbGraderApp,
    # BaseApp, NbConvertApp, BaseIPythonApplication, Application
    
    # List of file names or file globs to be ignored when copying directories.
    # c.FeedbackApp.ignore = ['.ipynb_checkpoints', '*.pyc', '__pycache__']
    
    # The export format to be used.
    # c.FeedbackApp.export_format = 'html'
    
    # Set the log level by value or name.
    # c.FeedbackApp.log_level = 30
    
    # Permissions to set on files output by nbgrader. The default is generally read-
    # only (444), with the exception of nbgrader assign, in which case the user also
    # has write permission.
    # c.FeedbackApp.permissions = 0
    
    # Whether to overwrite existing assignments/submissions
    # c.FeedbackApp.force = False
    
    #------------------------------------------------------------------------------
    # AssignApp configuration
    #------------------------------------------------------------------------------
    
    # AssignApp will inherit config from: BaseNbConvertApp, BaseNbGraderApp,
    # BaseApp, NbConvertApp, BaseIPythonApplication, Application
    
    # List of file names or file globs to be ignored when copying directories.
    # c.AssignApp.ignore = ['.ipynb_checkpoints', '*.pyc', '__pycache__']
    
    # Whether to create the assignment at runtime if it does not already exist.
    # c.AssignApp.create_assignment = False
    
    # Set the log level by value or name.
    # c.AssignApp.log_level = 30
    
    # Permissions to set on files output by nbgrader. The default is generally read-
    # only (444), with the exception of nbgrader assign, in which case the user also
    # has write permission.
    # c.AssignApp.permissions = 0
    
    # Whether to overwrite existing assignments/submissions
    # c.AssignApp.force = False
    
    #------------------------------------------------------------------------------
    # ValidateApp configuration
    #------------------------------------------------------------------------------
    
    # ValidateApp will inherit config from: BaseApp, NbConvertApp,
    # BaseIPythonApplication, Application
    
    # Set the log level by value or name.
    # c.ValidateApp.log_level = 30
    
    #------------------------------------------------------------------------------
    # AutogradeApp configuration
    #------------------------------------------------------------------------------
    
    # AutogradeApp will inherit config from: BaseNbConvertApp, BaseNbGraderApp,
    # BaseApp, NbConvertApp, BaseIPythonApplication, Application
    
    # Whether to create the student at runtime if it does not already exist.
    # c.AutogradeApp.create_student = False
    
    # Whether to overwrite existing assignments/submissions
    # c.AutogradeApp.force = False
    
    # Set the log level by value or name.
    # c.AutogradeApp.log_level = 30
    
    # Permissions to set on files output by nbgrader. The default is generally read-
    # only (444), with the exception of nbgrader assign, in which case the user also
    # has write permission.
    # c.AutogradeApp.permissions = 0
    
    # List of file names or file globs to be ignored when copying directories.
    # c.AutogradeApp.ignore = ['.ipynb_checkpoints', '*.pyc', '__pycache__']
    
    #------------------------------------------------------------------------------
    # ReleaseApp configuration
    #------------------------------------------------------------------------------
    
    # ReleaseApp will inherit config from: TransferApp, BaseNbGraderApp, BaseApp,
    # BaseIPythonApplication, Application
    
    # List of file names or file globs to be ignored when copying directories.
    # c.ReleaseApp.ignore = ['.ipynb_checkpoints', '*.pyc', '__pycache__']
    
    # Force overwrite existing files in the exchange.
    # c.ReleaseApp.force = False
    
    # The nbgrader exchange directory writable to everyone. MUST be preexisting.
    # c.ReleaseApp.exchange_directory = '/srv/nbgrader/exchange'
    
    # Timezone for recording timestamps
    # c.ReleaseApp.timezone = 'UTC'
    
    # Format string for timestamps
    # c.ReleaseApp.timestamp_format = '%Y-%m-%d %H:%M:%S %Z'
    
    # Set the log level by value or name.
    # c.ReleaseApp.log_level = 30
    
    #------------------------------------------------------------------------------
    # IncludeHeaderFooter configuration
    #------------------------------------------------------------------------------
    
    # A preprocessor for adding header and/or footer cells to a notebook.
    
    # IncludeHeaderFooter will inherit config from: NbGraderPreprocessor,
    # Preprocessor, NbConvertBase
    
    # Path to header notebook
    # c.IncludeHeaderFooter.header = ''
    
    # Path to footer notebook
    # c.IncludeHeaderFooter.footer = ''
    
    # Whether to use this preprocessor when running nbgrader
    # c.IncludeHeaderFooter.enabled = True
    
    #------------------------------------------------------------------------------
    # LockCells configuration
    #------------------------------------------------------------------------------
    
    # A preprocessor for making cells undeletable.
    
    # LockCells will inherit config from: NbGraderPreprocessor, Preprocessor,
    # NbConvertBase
    
    # Whether solution cells are undeletable
    # c.LockCells.lock_solution_cells = True
    
    # Whether grade cells are undeletable
    # c.LockCells.lock_grade_cells = True
    
    # Whether to use this preprocessor when running nbgrader
    # c.LockCells.enabled = True
    
    # Whether all assignment cells are undeletable
    # c.LockCells.lock_all_cells = False
    
    #------------------------------------------------------------------------------
    # ClearSolutions configuration
    #------------------------------------------------------------------------------
    
    # ClearSolutions will inherit config from: NbGraderPreprocessor, Preprocessor,
    # NbConvertBase
    
    # The comment mark to prefix solution delimiters
    # c.ClearSolutions.comment_mark = '#'
    
    # Whether to use this preprocessor when running nbgrader
    # c.ClearSolutions.enabled = True
    
    # The code snippet that will replace code solutions
    # c.ClearSolutions.code_stub = '# YOUR CODE HERE\nraise NotImplementedError()'
    
    # The delimiter marking the end of a solution (excluding comment mark)
    # c.ClearSolutions.end_solution_delimeter = '## END SOLUTION'
    
    # The text snippet that will replace written solutions
    # c.ClearSolutions.text_stub = 'YOUR ANSWER HERE'
    
    # The delimiter marking the beginning of a solution (excluding comment mark)
    # c.ClearSolutions.begin_solution_delimeter = '## BEGIN SOLUTION'
    
    #------------------------------------------------------------------------------
    # SaveAutoGrades configuration
    #------------------------------------------------------------------------------
    
    # Preprocessor for saving out the autograder grades into a database
    
    # SaveAutoGrades will inherit config from: NbGraderPreprocessor, Preprocessor,
    # NbConvertBase
    
    # Whether to use this preprocessor when running nbgrader
    # c.SaveAutoGrades.enabled = True
    
    #------------------------------------------------------------------------------
    # DisplayAutoGrades configuration
    #------------------------------------------------------------------------------
    
    # Preprocessor for displaying the autograder grades
    
    # DisplayAutoGrades will inherit config from: NbGraderPreprocessor,
    # Preprocessor, NbConvertBase
    
    # Warning to display when a cell passes (when invert=True)
    # c.DisplayAutoGrades.passed_warning = 'NOTEBOOK PASSED ON {num_passed} CELL(S)!'
    
    # Complain when cells pass, rather than fail.
    # c.DisplayAutoGrades.invert = False
    
    # Whether to use this preprocessor when running nbgrader
    # c.DisplayAutoGrades.enabled = True
    
    # Maximum line width for displaying code/errors
    # c.DisplayAutoGrades.width = 90
    
    # Don't complain if cell checksums have changed (if they are code grade cells)
    # or haven't changed (if they are markdown solution and grade cells)
    # c.DisplayAutoGrades.ignore_checksums = False
    
    # Warning to display when a cell fails.
    # c.DisplayAutoGrades.failed_warning = 'VALIDATION FAILED ON {num_failed} CELL(S)! If you submit\nyour assignment as it is, you WILL NOT receive full\ncredit.'
    
    # A string containing whitespace that will be used to indent code and errors
    # c.DisplayAutoGrades.indent = '    '
    
    # Warning to display when a cell has changed.
    # c.DisplayAutoGrades.changed_warning = "THE CONTENTS OF {num_changed} TEST CELL(S) HAVE CHANGED!\nThis might mean that even though the tests are passing\nnow, they won't pass when your assignment is graded."
    
    #------------------------------------------------------------------------------
    # ComputeChecksums configuration
    #------------------------------------------------------------------------------
    
    # A preprocessor to compute checksums of grade cells.
    
    # ComputeChecksums will inherit config from: NbGraderPreprocessor, Preprocessor,
    # NbConvertBase
    
    # Whether to use this preprocessor when running nbgrader
    # c.ComputeChecksums.enabled = True
    
    #------------------------------------------------------------------------------
    # SaveCells configuration
    #------------------------------------------------------------------------------
    
    # A preprocessor to save information about grade and solution cells.
    
    # SaveCells will inherit config from: NbGraderPreprocessor, Preprocessor,
    # NbConvertBase
    
    # Whether to use this preprocessor when running nbgrader
    # c.SaveCells.enabled = True
    
    #------------------------------------------------------------------------------
    # OverwriteCells configuration
    #------------------------------------------------------------------------------
    
    # A preprocessor to overwrite information about grade and solution cells.
    
    # OverwriteCells will inherit config from: NbGraderPreprocessor, Preprocessor,
    # NbConvertBase
    
    # Whether to use this preprocessor when running nbgrader
    # c.OverwriteCells.enabled = True
    
    #------------------------------------------------------------------------------
    # CheckCellMetadata configuration
    #------------------------------------------------------------------------------
    
    # A preprocessor for checking that grade ids are unique.
    
    # CheckCellMetadata will inherit config from: NbGraderPreprocessor,
    # Preprocessor, NbConvertBase
    
    # Whether to use this preprocessor when running nbgrader
    # c.CheckCellMetadata.enabled = True
    
    #------------------------------------------------------------------------------
    # Execute configuration
    #------------------------------------------------------------------------------
    
    # Execute will inherit config from: NbGraderPreprocessor, ExecutePreprocessor,
    # Preprocessor, NbConvertBase
    
    # The time to wait (in seconds) for output from executions.
    # c.Execute.timeout = 30
    
    # Whether to use this preprocessor when running nbgrader
    # c.Execute.enabled = True
    
    #------------------------------------------------------------------------------
    # GetGrades configuration
    #------------------------------------------------------------------------------
    
    # Preprocessor for saving grades from the database to the notebook
    
    # GetGrades will inherit config from: NbGraderPreprocessor, Preprocessor,
    # NbConvertBase
    
    # Whether to use this preprocessor when running nbgrader
    # c.GetGrades.enabled = True
    
    #------------------------------------------------------------------------------
    # ClearOutput configuration
    #------------------------------------------------------------------------------
    
    # ClearOutput will inherit config from: NbGraderPreprocessor,
    # ClearOutputPreprocessor, Preprocessor, NbConvertBase
    
    # Whether to use this preprocessor when running nbgrader
    # c.ClearOutput.enabled = True
    
    #------------------------------------------------------------------------------
    # LimitOutput configuration
    #------------------------------------------------------------------------------
    
    # Preprocessor for limiting cell output
    
    # LimitOutput will inherit config from: NbGraderPreprocessor, Preprocessor,
    # NbConvertBase
    
    # maximum number of lines of output (-1 means no limit)
    # c.LimitOutput.max_lines = 1000
    
    # maximum number of traceback lines (-1 means no limit)
    # c.LimitOutput.max_traceback = 100
    
    # Whether to use this preprocessor when running nbgrader
    # c.LimitOutput.enabled = True
    