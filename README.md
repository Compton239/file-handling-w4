def read_and_write_file():
    try:
        # Prompt user for input and output filenames
        input_filename = input("Enter the input filename: ")
        output_filename = input("Enter the output filename: ")

        # Read from input file
        with open(input_filename, 'r') as input_file:
            content = input_file.read()

        # Modify content (example: convert to uppercase)
        modified_content = content.upper()

        # Write to output file
        with open(output_filename, 'w') as output_file:
            output_file.write(modified_content)

        print(f"File successfully processed! Modified content written to {output_filename}")

    except FileNotFoundError:
        print(f"Error: The file '{input_filename}' was not found.")
    except PermissionError:
        print("Error: Permission denied while accessing the file.")
    except IOError as e:
        print(f"Error: An I/O error occurred: {e}")
    except Exception as e:
        print(f"Error: An unexpected error occurred: {e}")

# Run the function
if __name__ == "__main__":
    read_and_write_file()
