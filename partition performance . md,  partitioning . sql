ALTER TABLE bookings name RENAME TO bookings_old;
CREATE TABLE bookings(
    booking_id SERIAL PRIMARY KEY,
    user_id INT NOT NULL,
    property_id INT NOT NULL,
    start_date DATE NOT NULL,
    end_date DATE,
    status VARCHAR(50),
    created at TIMESTAMP DEFAULT CURRENT_TIMESTAP )
    PARTITION BY RANGE (start_date);
    CREATE TABLE bookings_2024 PARTITION OF bookings
    FOR VALUES FROM ('2024-01-01') TO ('2024-01-01');
    INSERT INTO bookings (booking_id,user_id,property_id,start_date,end_date)
    SELECT booking_id,user_id,property_id,start_date,end_date,status,created_at
    FROM bookings_old;
    DROP TABLE bookings_old;