Usage of gh_manager
===================

This guide provides practical examples on how to use **gh_manager** to automate various GitHub management tasks. Whether you're managing repositories, handling files, or managing GitHub Personal Access Tokens (PATs), **gh_manager** offers easy-to-use functions to simplify your workflows.

Repository Management
---------------------

### Deleting a Repository

To delete a repository from a GitHub organization or user account, use the `delete_repo` function:

.. code-block:: python

    from gh_manager.delete_repo import delete_repo

    # Delete a repository named 'example-repo' in the 'example-org' organization
    delete_repo('example-repo', 'example-org', 'your-github-token')

### Adding a User to an Organization

Add a user to a GitHub organization with the `add_user_to_org` function:

.. code-block:: python

    from gh_manager.org_username_add import add_user_to_org

    # Add user 'new-user' to 'example-org' organization with member role
    add_user_to_org('new-user', 'example-org', 'your-github-token')

File Management
---------------

### Adding a File to a Repository

To add a new file to a repository, use the `add_file_to_repo` function:

.. code-block:: python

    from gh_manager.repo_file_add import add_file_to_repo

    # Add a file named 'new-file.txt' with content to the main branch of 'example-repo'
    add_file_to_repo(
        repo_name='example-repo',
        org_name='example-org',
        file_path='new-file.txt',
        content='Hello, this is a new file!',
        commit_message='Add new file',
        token='your-github-token'
    )

### Updating a File in a Repository

Update an existing file in a repository using the `update_file_in_repo` function:

.. code-block:: python

    from gh_manager.repo_file_update import update_file_in_repo

    # Update 'existing-file.txt' with new content in the 'example-repo'
    update_file_in_repo(
        repo_name='example-repo',
        org_name='example-org',
        file_path='existing-file.txt',
        content='Updated content!',
        commit_message='Update existing file',
        token='your-github-token',
        sha='existing-file-sha'
    )

GitHub Personal Access Token Management
---------------------------------------

### Retrieving and Setting GitHub PAT

Manage your GitHub Personal Access Tokens using the `github_token_manager` module:

.. code-block:: python

    from gh_manager.github_token_manager import github_get_token, github_set_token

    # Retrieve the currently set GitHub PAT
    token = github_get_token()
    print(f"Current GitHub PAT: {token}")

    # Set a new GitHub PAT
    github_set_token('your-new-github-token')

### Testing and Validating a GitHub PAT

Check the validity of a GitHub PAT and see the associated scopes:

.. code-block:: python

    from gh_manager.github_token_manager import github_test_token, github_token_scopes

    # Test if the GitHub PAT is valid
    is_valid = github_test_token()
    print(f"Is the GitHub PAT valid? {is_valid}")

    # Get the scopes of the current GitHub PAT
    scopes = github_token_scopes()
    print(f"Token scopes: {scopes}")

Additional Resources
--------------------

- **API Documentation**: For a detailed list of all available functions and their parameters, refer to the `API Documentation <api.html>`_ section.
- **GitHub Repository**: Visit the `gh_manager GitHub Repository <https://github.com/Gchism94/gh_manager>`_ for source code, issues, and contributions.

This guide covers the basic usage scenarios for **gh_manager**. Explore the API documentation for a complete reference of all available functions and features.
