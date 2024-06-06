# terraform-provider-pyexec

This project allow to execute python scripts using terraform.

The key to use this module is to put your python script in the same folder, this could be as example:

    terraform {
        required_providers {
            python = {
                source = "joaqquin89/python"
            }
        }
    }

	resource "python_exec" "main" {
        pyversion = "v2"
	    script    = "pythonscript.py"
	    args      = "<ARG1> <ARG2>....."
	}

*** the arguments depends on the script that you will execute

In case the if you want to catch the output, you can use the atribute `exec_py`:

	output "script_result" {
	    value = python_exec.main.exec_py
	}
